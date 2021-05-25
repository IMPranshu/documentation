---
# Copyright Verizon Media. Licensed under the terms of the Apache 2.0 license. See LICENSE in the project root.
title: FAQ - frequently asked questions
style: faq
---

Refer to [Vespa Support](https://vespa.ai/support) for more support options.

* TOC
{:toc}

---

{:.faq-section}
### Ranking

#### Does Vespa support a flexible ranking score?
<a href="ranking.html">Ranking</a> is maybe the best Vespa feature -
we like to think of it as scalable, online computation.
A rank profile is where the application's logic is implemented,
supporting simple types like <code>double</code> and complex types like <code>tensor</code>.
Supply ranking data in queries in query features (e.g. different weights per customer),
or look up in a <a href="searcher-development.html">Searcher</a>.
Typically a document (e.g. product) "feature vector"/"weights" will be compared to a user-specific vector (tensor).

#### Where would customer specific weightings be stored?
Vespa doesn't have specific support for storing customer data as such.
You can store this data as a separate document type in Vespa and look it up before passing the query,
or store this customer meta-data as part of the other meta-data for the customer
(i.e. login information) and pass it along the query when you send it to the backend.
Find an example on how to look up data in
<a href="https://github.com/vespa-engine/sample-apps/tree/master/vespa-cloud/album-recommendation-docproc">
album-recommendation-docproc</a>.
</p>

#### How to create a tensor on the fly in the ranking expression?
Create a tensor in the ranking function from arrays or weighted sets using <code>tensorFrom...</code> functions - see
<a href="reference/rank-features.html#document-features">document features</a>.

{:.faq-section}
### Documents

#### What limits apply to json document size?
There is no hard limit.
Vespa requires a document to be able to load into memory in serialized form.
Vespa is not optimized for huge documents.

#### Can a document have lists (key value pairs)?
E.g. a product is offered in a list of stores with a quantity per store.
Use <a href="schemas.html#multivalue-fields">multivalue fields</a> (array of struct)
or <a href="parent-child.html">parent child</a>.
Which one to chose depends on use case, see discussion the the latter link.

#### Does a whole document need to be updated and re-indexed?
E.g, price and quantity available per store may change often vs the actual product attributes.
Vespa supports [partial updates](reads-and-writes.html) of documents.
Also, the parent/child feature is implemented to support use-cases where child elements are updated frequently,
while a more limited set of parent elements are updated less frequently.

#### What ACID guarantees if any does Vespa provide for single writes / updates / deletes vs batch operations etc?
See <a href="content/consistency.html">Vespa Consistency Model</a>.
Vespa is not transactional in the traditional sense, it doesn't have strict ACID guarantees.
Vespa is designed for high performance use-cases with eventual consistency
as an acceptable (and to some extent configurable) trade-off.

#### Does vespa support wildcard fields? 
Wildcard fields are not supported in vespa. Workaround would be to use maps to store the wildcard fields. Map needs 
to be defined with indexing attribute and hence will be stored in memory. 
Refer to [map](reference/schema-reference.html#type:map)

#### What is the recommended redundant/searchable copy when using grouping distribution? 
Grouping is used to reduce search latency. When using grouped distribution content is distributed to a configured set of groups, 
such that the entire document collection is contained in each group. Setting the redundancy and searchable copies equal to the number 
of groups ensures that data can be queried from all of the group.

### Is there any size limitation in multivalued fields? 
No limit, except memory

#### Can we set a limit for the number of elements that can be stored in an array?
Implement a [document processor](document-processing.html) for this.

{:.faq-section}
### Query

#### Is hierarchical facets supported?
Facets is called <a href="grouping.html">grouping</a> in Vespa.
Groups can be multi-level.

#### Is filters supported?
Add filters to the query using <a href="query-language.html">YQL</a>
using boolean, numeric and <a href="text-matching-ranking.html">text matching</a>.

#### How to query for similar items?
One way is to describe items using tensors and query for the
<a href="reference/query-language-reference.html#nearestneighbor">nearest neighbor</a> -
using full precision or approximate (ANN) - the latter is used when the set is too large for an exact calculation.
Apply filters to the query to limit the neighbor candidate set.
Using <a href="multivalue-query-operators.html">dot products</a> or
<a href="using-wand-with-vespa.html">weak and</a> are alternatives.

#### Stop-word support?
Vespa does not have a stop-word concept inherently.
See the <a href="https://github.com/vespa-engine/sample-apps/pull/335/files">sample app</a>
for how to use <a href="reference/query-language-reference.html#annotations">filter terms</a>.

<!-- Feed but cannot see - doc selection/expiry -->


{:.faq-section}
### Text Search

#### Does Vespa support addition of flexible NLP processing for documents and search queries?
E.g. integrating NER, word sense disambiguation, specific intent detection.
Vespa supports these things well:
<ul>
  <li><a href="searcher-development.html">Query (and result) processing</a></li>
  <li><a href="document-processing.html">Document processing</a>
    and <a href="annotations.html">annotations</a>
    on document processors working on semantic annotations of text</li>
</ul>

#### Does Vespa support customization of the inverted index?
<em>E.g. instead of using terms or n-grams as the unit, we might use terms with specific word senses
(e.g. bark (dog bark) vs. bark (tree bark), or BCG (company) vs. BCG (vaccine name).</em>
Creating a new index <em>format</em> means changing the core.
However, for the examples above, one just need control over the tokens which are indexed (and queried).
That is easily done in some Java code.
The simplest way to do this is to plug in a <a href="linguistics.html">custom tokenizer</a>.
That gets called from the query parser and bundled linguistics processing
<a href="searcher-development.html">Searchers</a>
as well as the <a href="document-processing.html">Document Processor</a>
creating the annotations that are consumed by the indexing operation.
Since all that is Searchers and Docprocs which you can replace and/or add custom components before and after,
you can also take full control over these things without modifying the platform itself.

#### Does vespa provide any support for named entity extraction?
It provides the building blocks but not an out of the box solution.
We can write a [Searcher](searcher-development.html) to detect query-side entities and rewrite the query, 
and a [DocProc](document-processing.html) if we want to handle them in some special way on the indexing side.

#### Does vespa provide support for text extraction?
You can write a document processor for text extraction but Vespa doesn’t provide it out of the box.

{:.faq-section}
### Programming Vespa

<!--p id="programming-vespa-1"><strong>How to add custom code to a Vespa application?
</p-->

#### is Python plugins supported / is there a scripting language?
Plugins have to run in the JVM - <a href="https://www.jython.org/">jython</a> might be an alternative,
however Vespa Team has no experience with it.
Vespa does not have a language like
<a href="https://www.elastic.co/guide/en/elasticsearch/reference/master/modules-scripting-painless.html">painless</a> -
it is more flexible to write application logic in a JVM-supported language, using
<a href="searcher-development.html">Searchers</a>
and <a href="document-processing.html">Document Processors</a>.

<!--p id="programming-vespa-3" style="margin-bottom: 0px;"><strong>Is there a way to check if this component is alive or not?
<a href="jdisc/container-components.html">Component</a> lifecycle:
<ol>
  <li>Old components are alive</li>
  <li>Deployment occurs</li>
  <li>New components are constructed</li>
  <li>Old components are deconstructed</li>
  <li>Deployment is complete</li>
  <li>Only new components are alive</li>
</ol-->
<!-- ToDo: move this to the doc itself and link from here - and add something useful ... -->


{:.faq-section}
### Performance

#### What is the latency of documents being ingested vs indexed and available for search?
Vespa has a near real-time indexing core with typically sub-second latencies from ingest to indexed.
This depends on the use-case, available resources and how the system is tuned.
Some more examples and thoughts can be found in the
<a href="performance/sizing-search.html">scaling guide</a>.

#### Is there a batch ingestion mode, what limits apply?
Vespa does not have a concept of "batch ingestion"
as it contradicts many of the core features that are the strengths of Vespa,
including <a href="elastic-vespa.html">serving elasticity</a> and sub-second indexing latency.
That said, we have numerous use-cases in production that do high throughput updates to large parts of the (sometimes entire) document set.
In cases where feed throughput is more important than indexing latency, you can tune this to meet your requirements.
Some of this is detailed in the <a href="performance/sizing-feeding.html">feed sizing guide</a>.

#### Can the index support up to 512GB index size in memory?
Yes. The <a href="proton.html">content node</a>
is implemented in C++ and not memory constrained other than what the operating system does.

<!--p id="performance-4"><strong>How to optimise feeding from a Grid?
</p-->

#### Get request for a document when document is not in sync in all the replica nodes? 
If the replicas are in sync the request is only sent to the primary content node. Otherwise it's sent to several nodes, depending on replica metadata. 
Example: if a bucket has 3 replicas A, B, C and A & B both have metadata state X and C has metadata state Y, a request will be sent to A and C (but not B since it has the same state as A and would therefore not return a potentially different document)

{:.faq-section}
### Administration

#### How fast can nodes be added and removed from a running cluster?
<a href="elastic-vespa.html">Elasticity</a> is a core Vespa strength -
easily add and remove nodes with minimal (if any) serving impact.
The exact time needed depends on how much data will need to be migrated in the background for the system to converge to
<a href="content/idealstate.html">ideal data distribution</a>.

#### Should Vespa API search calls be load balanced or does Vespa do this automatically?
You will need to load balance incoming requests between the nodes running the
<a href="overview.html">stateless Java container cluster(s)</a>.
This can typically be done using a simple network load balancer available in most cloud services.
This is included when using <a href="https://cloud.vespa.ai/">Vespa Cloud</a>,
with an already load balanced HTTPS endpoint - both locally within the region and globally across regions.

#### Supporting index partitions
<a href="performance/sizing-search.html">Search sizing</a> is the intro to this.
Topology matters, and this is much used in the high-volume Vespa applications to optimise latency vs. cost

#### Can a running cluster be upgraded with zero downtime?
With <a href="https://cloud.vespa.ai/">Vespa Cloud</a>,
we do automated background upgrades daily without noticeable serving impact.
If you host Vespa yourself, you can do this, but need to implement the orchestration logic necessary to handle this.
The high level procedure is found in <a href="operations/live-upgrade.html">live-upgrade</a>.

#### Can Vespa be deployed multi-region?
<a href="https://cloud.vespa.ai/en/reference/zones">Vespa Cloud</a> has integrated support - query a global endpoint.
Writes will have to go to each zone.
There is no auto-sync between zones.

#### Can Vespa serve an Offline index?
Building indexes offline requires the partition layout to be known in the offline system,
which is in conflict with elasticity and auto-recovery
(where nodes can come and go without service impact).
It is also at odds with realtime writes.
For these reasons, it is not recommended, and not supported.

#### Does vespa give us any tool to browse the index and attribute data?
No. Use [visiting](content/visiting.html) to dump all or a subset of documents.
See [dumping-data](https://cloud.vespa.ai/en/dumping-data) for a sample script.

#### What is the response when data is written only on some of the nodes and not on all of the replica nodes (Based on the redundancy count of the content cluster)? 
Failure response will be given in case the document is not written on some of the replica nodes. 

#### When the doc is not written to some of the nodes will the document become available due to replica reconciliation? 
Primary behavior is that the write will be rolled back on the succeeding replicas, but there are edge case scenarios where you get 
a failure response when the write ends up being persisted. This might happen when the document gets written to the content node 
storing the active copy of the bucket.

#### Does vespa provide soft delete functionality?
Yes just add a "deleted" attribute, add [fast-search](attributes.html#fast-search) on it
and create a searcher which adds an “andnot deleted” item to queries.

#### Can we configure a grace period for bucket distribution so that buckets are not redistributed as soon as a node goes down? 
You can set a [transition-time](reference/services-content.html#transition-time) in services.xml to tell the cluster controller how long a node is to be kept in maintenance mode before being automatically marked down.
