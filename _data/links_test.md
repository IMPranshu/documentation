# Copyright Yahoo. Licensed under the terms of the Apache 2.0 license. See LICENSE in the project root.
docs:
  - title: GETTING STARTED
    documents:
      - page: Introduction
        url: /
      - page: Vespa Overview
        url: /en/overview.html
      - page: Features
        url: /en/features.html
      - page: Getting Started
        url: /en/getting-started.html
      - page: Getting Started with Ranking
        url: /en/getting-started-ranking.html
      - page: Quick Start
        url: /en/vespa-quick-start.html
      - page: Frequently Asked Questions
        url: /en/faq.html
      - page: Tutorials
        url: /en/tutorials/
      - page: Vespa CLI
        url: /en/vespa-cli.html
      - page: Vespa API and Interfaces
        url: /en/api.html
      - page: "Use case: Shopping"
        url: /en/use-case-shopping.html
      - page: "Use case: Question-Answering"
        url: /en/use-case-question-answering.html
      - page: "Use case: Text-Image Search"
        url: /en/use-case-text-image-search.html
      - page: Build and install Vespa
        url: /en/build-install-vespa.html

  - title: DOCUMENTS AND SCHEMAS
    documents:
      - page: Documents
        url: /en/documents.html
      - page: Schemas
        url: /en/schemas.html
      - page: Parent/Child
        url: /en/parent-child.html
      - page: Annotations API
        url: /en/annotations.html
      - page: Concrete document types
        url: /en/concrete-documents.html

  - title: READS AND WRITES
    documents:
      - page: Reads and Writes
        url: /en/reads-and-writes.html
      - page: /document/v1
        url: /en/document-v1-api-guide.html
      - page: Visiting
        url: /en/content/visiting.html
      - page: Vespa Feed Client
        url: /en/vespa-feed-client.html
      - page: Vespa HTTP Client
        url: /en/vespa-http-client.html
      - page: Feed using Hadoop, Pig, Oozie
        url: /en/feed-using-hadoop-pig-oozie.html
      - page: Indexing
        url: /en/indexing.html
      - page: Document API
        url: /en/document-api-guide.html
      - page: Partial Updates
        url: /en/partial-updates.html

  - title: QUERIES
    documents:
      - page: Query API
        url: /en/query-api.html
      - page: Vespa Query Language
        url: /en/query-language.html
      - page: Grouping Information in Results
        url: /en/grouping.html
      - page: Federation
        url: /en/federation.html
      - page: Query Profiles
        url: /en/query-profiles.html
      - page: Nearest Neighbor Search
        url: /en/nearest-neighbor-search.html
      - page: Approximate Nearest Neighbor Search
        url: /en/approximate-nn-hnsw.html
      - page: Geo Search
        url: /en/geo-search.html
      - page: Predicate Fields
        url: /en/predicate-fields.html
      - page: Streaming Search
        url: /en/streaming-search.html
      - page: Document Summaries
        url: /en/document-summaries.html
      - page: Result Renderers
        url: /en/result-rendering.html
      - page: Page Templates
        url: /en/page-templates.html

  - title: RANKING AND ML MODELS
    documents:
      - page: Ranking Introduction
        url: /en/ranking.html
      - page: Rank Features and Expressions
        url: /en/ranking-expressions-features.html
      - page: Multivalue Query Operators
        url: /en/multivalue-query-operators.html
      - page: Tensor User Guide
        url: /en/tensor-user-guide.html
      - page: Tensor Examples
        url: /en/tensor-examples.html
      - page: Phased Ranking
        url: /en/phased-ranking.html
      - page: Ranking With TensorFlow Models
        url: /en/tensorflow.html
      - page: Ranking With ONNX Models
        url: /en/onnx.html
      - page: Ranking With XGBoost Models
        url: /en/xgboost.html
      - page: Ranking With LightGBM Models
        url: /en/lightgbm.html
      - page: Stateless model evaluation
        url: /en/stateless-model-evaluation.html
      - page: Text Ranking
        url: /en/text-matching-ranking.html
      - page: Ranking With BM25
        url: /en/reference/bm25.html
      - page: Ranking With nativeRank
        url: /en/nativerank.html
      - page: Semantic Retrieval for Q/A Applications
        url: /en/semantic-qa-retrieval.html
      - page: Learning to Rank
        url: /en/learning-to-rank.html
      - page: Accelerated OR search using the WAND algorithm
        url: /en/using-wand-with-vespa.html

  - title: LINGUISTICS AND TEXT PROCESSING
    documents:
      - page: Linguistics in Vespa
        url: /en/linguistics.html
      - page: Query Rewriting
        url: /en/query-rewriting.html
      - page: Embedding text
        url: /en/embedding.html
      - page: Troubleshooting character encoding
        url: /en/troubleshooting-encoding.html

  - title: TUTORIALS AND QUICK STARTS
    documents:
      - page: "News 1: Getting Started"
        url: /en/tutorials/news-1-getting-started.html
      - page: "News 2: Application Packages, Feeding, Query"
        url: /en/tutorials/news-2-basic-feeding-and-query.html
      - page: "News 3: Sorting, Grouping and Ranking"
        url: /en/tutorials/news-3-searching.html
      - page: "News 4: Embeddings"
        url: /en/tutorials/news-4-embeddings.html
      - page: "News 5: Partial Updates, ANNs, Filtering"
        url: /en/tutorials/news-5-recommendation.html
      - page: "News 6: Custom Searchers, Document Processors"
        url: /en/tutorials/news-6-recommendation-with-searchers.html
      - page: "News 7: Parent-Child, Tensor Ranking"
        url: /en/tutorials/news-7-recommendation-with-parent-child.html
      - page: Models Hot Swap
        url: /en/tutorials/models-hot-swap.html
      - page: Text Search
        url: /en/tutorials/text-search.html
      - page: Text Search ML
        url: /en/tutorials/text-search-ml.html
      - page: Semantic Text Search
        url: /en/tutorials/text-search-semantic.html
      - page: Quick Start Java
        url: /en/vespa-quick-start-java.html
      - page: Quick Start Vagrant
        url: /en/vespa-quick-start-vagrant.html
      - page: Quick Start Kubernetes
        url: /en/vespa-quick-start-kubernetes.html
      - page: Quick Start Multinode AWS
        url: /en/vespa-quick-start-multinode-aws.html
      - page: Quick Start Multinode AWS ECS
        url: /en/vespa-quick-start-multinode-aws-ecs.html

  - title: DEVELOPING APPLICATIONS AND PLUGINS
    documents:
      - page: Developer Guide
        url: /en/developer-guide.html
      - page: Application Packages
        url: /en/cloudconfig/application-packages.html
      - page: Application Testing
        url: /en/testing.html
      - page: Java Serving Container
        url: /en/jdisc/
      - page: Container Components
        url: /en/jdisc/container-components.html
      - page: Request-Response Processing
        url: /en/jdisc/processing.html
      - page: Searcher Development
        url: /en/searcher-development.html
      - page: Document Processor Development
        url: /en/document-processing.html
      - page: Developing Web Service Applications
        url: /en/developing-web-services.html
      - page: Component Injection
        url: /en/jdisc/injecting-components.html
      - page: Chained Components
        url: /en/chained-components.html
      - page: Configuring Java components
        url: /en/configuring-components.html
      - page: Bundles
        url: /en/components/bundles.html
      - page: Using ZooKeeper
        url: /en/using-zookeeper.html
      - page: Developing request handlers
        url: /en/jdisc/developing-request-handlers.html
      - page: Building an HTTP API using request handlers and processors
        url: /en/jdisc/http-api-tutorial.html
      - page: Configuring Http Servers and Filters
        url: /en/jdisc/http-server-and-filters.html
      - page: XML Processing
        url: /en/jdisc/jax.html
      - page: Using Libraries for Pluggable Frameworks
        url: /en/jdisc/pluggable-frameworks.html
      - page: Developing client providers
        url: /en/reference/developing-client-providers.html
      - page: Developing server providers
        url: /en/reference/developing-server-providers.html
      - page: Server Tutorial
        url: /en/reference/server-tutorial.html

  - title: CONFIGURATION
    documents:
      - page: Configuration Intro
        url: /en/cloudconfig/config-introduction.html
      - page: Deploy API
        url: /en/cloudconfig/deploy-rest-api-v2.html
      - page: HTTP Config API
        url: /en/cloudconfig/config-rest-api-v2.html
      - page: Config API
        url: /en/cloudconfig/configapi-dev.html
      - page: Developing Config Model Plugins
        url: /en/cloudconfig/cloudconfig-model-plugins.html
      - page: Developing with the Java Cloud Config API
        url: /en/cloudconfig/configapi-dev-java.html
      - page: Using the C++ Cloud config API
        url: /en/cloudconfig/configapi-dev-cpp.html
      - page: Configuration Servers
        url: /en/cloudconfig/configuration-server.html
      - page: Tenant API
        url: /en/cloudconfig/tenant-rest-api.html
      - page: Routing
        url: /en/routing.html

  - title: THE CONTENT LAYER
    documents:
      - page: Elastic Vespa
        url: /en/elastic-vespa.html
      - page: Proton
        url: /en/proton.html
      - page: Content Nodes and States
        url: /en/content/content-nodes.html
      - page: Consistency Model
        url: /en/content/consistency.html
      - page: Distribution Algorithm
        url: /en/content/idealstate.html
      - page: Buckets
        url: /en/content/buckets.html
      - page: State API
        url: /en/content/api-state-rest-api.html

  - title: PERFORMANCE AND TUNING
    documents:
      - page: Performance intro
        url: /en/performance/
      - page: Serving Sizing Guide
        url: /en/performance/sizing-search.html
      - page: Feed Sizing Guide
        url: /en/performance/sizing-feeding.html
      - page: Sizing Examples
        url: /en/performance/sizing-examples.html
      - page: Document Attributes
        url: /en/attributes.html
      - page: Benchmarking
        url: /en/performance/vespa-benchmarking.html
      - page: Profiling
        url: /en/performance/profiling.html
      - page: Container Tuning
        url: /en/performance/container-tuning.html
      - page: Rate-Limiting Search Requests
        url: /en/performance/rate-limiting-searcher.html
      - page: HTTP/2
        url: /en/performance/http2.html
      - page: Graceful Search Coverage Degradation
        url: /en/graceful-degradation.html
      - page: Caches
        url: /en/performance/caches-in-vespa.html
      - page: HTTP Performance Testing
        url: /en/performance/container-http.html
      - page: Feature Tuning
        url: /en/performance/feature-tuning.html
      - page: Valgrind
        url: /en/performance/valgrind.html

  - title: OPERATIONS AND PROCEDURES
    documents:
      - page: Vespa Command-line Tools
        url: /en/reference/vespa-cmdline-tools.html
      - page: Vespa Metrics
        url: /en/reference/metrics.html
      - page: Log Files
        url: /en/reference/logs.html
      - page: Files, Processes, Ports, Environment
        url: /en/reference/files-processes-and-ports.html
      - page: Monitoring
        url: /en/operations/monitoring.html
      - page: Node Setup
        url: /en/operations/node-setup.html
      - page: Multinode Systems
        url: /en/operations/multinode-systems.html
      - page: Inspecting Vespa Java Services
        url: /en/inspecting-java-services.html
      - page: Docker Containers in Production
        url: /en/docker-containers-in-production.html
      - page: Securing a Vespa installation
        url: /en/securing-your-vespa-installation.html
      - page: mTLS
        url: /en/mtls.html
      - page: Access Logging
        url: /en/access-logging.html
      - page: Config sentinel
        url: /en/config-sentinel.html
      - page: Config Proxy
        url: /en/operations/config-proxy.html
      - page: Service Location Broker
        url: /en/slobrok.html
      - page: Administrative Procedures
        url: /en/operations/admin-procedures.html
      - page: Change from attribute to index procedure
        url: /en/operations/procedure-change-attribute-index.html
      - page: Live Vespa upgrade procedure
        url: /en/operations/live-upgrade.html
      - page: Batch delete
        url: /en/operations/batch-delete.html
      - page: Feed block
        url: /en/operations/feed-block.html
      - page: Reindexing
        url: /en/operations/reindexing.html

  - title: CONFIGURATION REFERENCE
    documents:
      - page: Application Package Reference
        url: /en/reference/application-packages-reference.html
      - page: Schema Reference
        url: /en/reference/schema-reference.html
      - page: services.xml
        url: /en/reference/services.html
      - page: services.xml - admin
        url: /en/reference/services-admin.html
      - page: services.xml - container
        url: /en/reference/services-container.html
      - page: services.xml - content
        url: /en/reference/services-content.html
      - page: services.xml - docproc
        url: /en/reference/services-docproc.html
      - page: services.xml - http
        url: /en/reference/services-http.html
      - page: services.xml - processing
        url: /en/reference/services-processing.html
      - page: services.xml - routing
        url: /en/reference/services-routing.html
      - page: services.xml - search
        url: /en/reference/services-search.html
      - page: hosts.xml
        url: /en/reference/hosts.html
      - page: validation-overrides.xml
        url: /en/reference/validation-overrides.html
      - page: Indexing Language Reference
        url: /en/reference/advanced-indexing-language.html
      - page: Custom Configuration File Reference
        url: /en/reference/config-files.html
      - page: mTLS Reference
        url: /en/reference/mtls.html
      - page: Routingpolicies Reference
        url: /en/reference/routingpolicies.html
      - page: Internal Configuration File Reference
        url: /en/reference/internal-config-files.html
      - page: Healthchecks Reference
        url: /en/reference/healthchecks.html
      - page: Config Inspect Interface
        url: /en/reference/state-config-inspect.html

  - title: RANKING REFERENCE
    documents:
      - page: Ranking Expressions
        url: /en/reference/ranking-expressions.html
      - page: Tensor Evaluation Reference
        url: /en/reference/tensor.html
      - page: nativeRank Reference
        url: /en/reference/nativerank.html
      - page: Rank Feature Reference
        url: /en/reference/rank-features.html
      - page: String Segment Match
        url: /en/reference/string-segment-match.html
      - page: Rank Feature Configuration
        url: /en/reference/rank-feature-configuration.html
      - page: Rank Types
        url: /en/reference/rank-types.html
      - page: Stateless Model Reference
        url: /en/reference/stateless-model-reference.html

  - title: QUERIES AND RESULTS REFERENCE
    documents:
      - page: Query API Reference
        url: /en/reference/query-api-reference.html
      - page: Query Language Reference
        url: /en/reference/query-language-reference.html
      - page: Simple Query Language Reference
        url: /en/reference/simple-query-language-reference.html
      - page: Select Reference
        url: /en/reference/select-reference.html
      - page: Grouping Reference
        url: /en/reference/grouping-syntax.html
      - page: Sorting Reference
        url: /en/reference/sorting.html
      - page: Query Profile Reference
        url: /en/reference/query-profile-reference.html
      - page: Semantic Rule Language Reference
        url: /en/reference/semantic-rules.html
      - page: Default JSON Result Format
        url: /en/reference/default-result-format.html
      - page: Page Templates Syntax
        url: /en/reference/page-templates-syntax.html
      - page: Page Result Format
        url: /en/reference/page-result-format.html
      - page: Inspecting Structured Data in a Searcher
        url: /en/reference/inspecting-structured-data.html
      - page: Statistics API - Generating statistics in a plugin
        url: /en/reference/statistics-api.html
      - page: Low-level request handler APIs
        url: /en/reference/low-level-request-handlers.html

  - title: DOCUMENT API AND LANGUAGES REFERENCE
    documents:
      - page: /document/v1 API reference
        url: /en/reference/document-v1-api-reference.html
      - page: Document JSON Format
        url: /en/reference/document-json-format.html
      - page: Document Field Path Syntax
        url: /en/reference/document-field-path.html
      - page: Document Selector Language
        url: /en/reference/document-select-language.html

  - title: COMPONENT REFERENCE
    documents:
      - page: Component Reference
        url: /en/reference/component-reference.html

  - title: UTIL AND LIBRARIES
    documents:
      - page: Vespa Command-line Tools
        url: /en/reference/vespa-cmdline-tools.html
      - page: Predicate Search Java Library
        url: /en/boolean-library.html
      - page: "pyvespa: Connect to a Running Vespa Instance"
        url: /en/pyvespa/connect-to-vespa-instance.html
      - page: "pyvespa: Create a Text Search Application"
        url: /en/pyvespa/create-text-app.html
      - page: "pyvespa: Deploy to Docker"
        url: /en/pyvespa/deploy-vespa-docker.html
      - page: "pyvespa: Document Operations"
        url: /en/pyvespa/feed-query-and-other-document-operations.html

  - title: ABOUT THIS SITE
    documents:
      - page: Documentation Conventions
        url: /en/introduction-to-documentation.html
      - page: Contributing to Vespa
        url: /en/contributing.html