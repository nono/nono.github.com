---
date: 2014-10-14
title: "When one sidekiq instance is not enough"
categories:
- Ruby
---
In the Ruby world, there was a popular gem for queueing jobs: resque. With one
call to a ruby method, you can put a job in redis. And a daemon, called a
worker, can take a job from redis, process it, and then go to the next job.

It works well, but when you want to scale and process more than one job in
parallel, you have to launch several worker processes, and it can take a lot
of memory. So, Mike Perham wrote a new gem: Sidekiq. It does the same thing
than resque, but it enables to perform multiple jobs inside a process by using
threads. And threads take a lot less memory than processes.

Sidekiq became more popular than resque, and it is well summed up by its
headline:

> _What if 1 Sidekiq process could do the work of 20 Resque processes?_

But, is it true? Well, it depends. For most tasks, like sending mails or
fetching things from internet, it works really nice.

In some cases, like CPU-intensive tasks, it's more complicated. The official
Ruby interpreter (MRI) has something called the Global Interpreter Lock (GIL).
Its role is to avoid that code from one thread can mess another thread. For
that, when a thread wants to execute Ruby code, it has to first take the GIL.
And after some time, it will release the GIL, so that another thread can take
it and execute other Ruby code: it's cooperative scheduling. There are a few
exceptions to this rule: waiting the response from a database or an HTTP
connection can be made by a threading that doesn't have the GIL.

So, what to do when you are in one those cases?

First, you can try another interpreter: JRuby, for example, has no GIL and can
run several threads over all your cores. JRuby is also said to be a bit faster
than MRI, but it varies a lot from one use case to another. YMMV.

Last week, I had a sidekiq instance running with MRI that take 100% of CPU, ie
it used only one core from the 8 there. So, i tried JRuby (and it wasn't
painless because of some incompatible gems). Yeah, my sidekiq instance running
with JRuby can use all the 8 cores. But it was still processing jobs 30%
slower than MRI... So, I'm keeping MRI and I will use the same strategy that
resque: running several processes. With multiple sidekiq instance, it's
possible to use more than one core, even on MRI.
