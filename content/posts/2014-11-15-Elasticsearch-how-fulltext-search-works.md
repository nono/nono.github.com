---
date: 2014-11-15
title: "Elasticsearch: how fulltext search works?"
categories:
- elasticsearch
---

[Elasticsearch](http://www.elasticsearch.org/) is distributed RESTful search
and analytics. One of its most known feature is fulltext search, which uses
Lucene under the covers. But it's not that easy to use it and understand what
you're doing. This post is a way for me to make my mind clear and explain
what I understand of how it works.

In the SQL world, you have a database, within it you can create some tables,
with typed columns. Then you insert some rows in your tables and make some
queries to return results. If you want to make your queries faster, you can
add an index.

**Please forget it!** In Elasticsearch, an index is more or less the same that
a table. And the way you index your data will influence the results of your
queries.


## Create an index

Let's start. If we want to store some data and make queries on them, we have
to put the data somewhere. In Elasticsearch, the right place for that is an
index. So, let's create an index. It's easy, the only mandatory thing is a
name for it. As said before, Elasticsearch is restful, so we can create the
index with curl. For example:

```sh
$ curl -XPUT 'http://localhost:9200/languages/'
```


## Mapping

* Multi-fields
* Analyzer -> Tokenizer + Filters
* Not-analyzed -> for facets and aggregations
* `_all`


## Put some documents in your index


## Send a query

* query vs filters
* analyzing the fulltext query


## Matching data


## Score, with Tf/idf

* http://www.elasticsearch.org/guide/en/elasticsearch/guide/current/practical-scoring-function.html
* Shards


## TODO

* examples
* diagrams
* https://www.found.no/play


## Conclusion

We have seen of an index is created with a mapping, how documents are indexed,
how queries is also analyzed and how the documents are scored. This is just a
small set a feature among all the things that Elasticsearch can do. But I hope
it will help you to understand a bit better how to create your mapping and
format your queries.

A last advice: don't expect to control everything. You are no longer in a
binary world where a set of data (a row in SQL, a document in Elasticsearch)
will either match or not match the query. In Elasticsearch, the document will
have a score for a query that depends of many things (some of them are how the
documents are split in shards). And even without that, it's very complicated
to analyze what a user wanted when he typed its query.
