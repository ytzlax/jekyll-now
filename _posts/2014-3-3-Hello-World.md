---
layout: post
title: What new in elasticsearch 6
---

Elasticsearch and kibana 6 is almost here, in the next lines I will mark new changes.

Sparse Doc values
Doc value is one of the data access pattern that elasticsearch using, doc value helps elasticsearch to be strong in sorting and aggregation.

Imagine we have the next documents:

Name
Gender
Twitter account
Josh
Male


Noga
Female
@Noga
Haim
Male


Jastin
Male
@Jastin

Elasticsearch takes this documents and store them in the next pattern:

Field
Doc1
Doc2
Doc3
Doc4
Name.keyword
Josh
Noga
Haim
Jastin
Gender.keyword
Male
Female
Male
Male
Twitter account.keyword


@Noga


@Jastin

As we see not all the documents have Twitter account fields, that causes a waste of space.
In elasticsearch 6 we have the support of sparse doc values that is a new encoding format that saves disk space and file system cache.

Index Sorting
The search of elasticsearch is very fast, but can it be even faster?
The answer is yes.
When we search, elastic go through all documents, sort the result and return only the top X result.
So if we could sort the documents before the search requests,all the process will be faster.
Here come “index sorting”, that permit us to sort the documents already at the index time, and to do so we need to choose the most frequent field search and sort by this field.

Removal Of Mapping Types
This is the most important change in elasticsearch 6.
From now on index can have only one type and
when indexing document we don't need to specifying the type.
The question now is how parent child mapping will be?
I hope writing it soon in my next blog.


Kibana 6

In kibana 6 we also have cool things.

Coordinate Map
Kibana team add the option to filter by drawing polygon on the map.

Dashboard
Now we can view a dashboard in full screen mode.

Visualisation
New visualisations: 
Gauge chart 
Region map











