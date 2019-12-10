## What is Prometheus?

[Prometheus](https://github.com/prometheus) is an open-source systems monitoring and alerting toolkit originally built at [SoundCloud](https://soundcloud.com). Since its inception in 2012, many companies and organizations have adopted Prometheus, and the project has a very active developer and user [community](/community). It is now a standalone open source project and maintained independently of any company. To emphasize this, and to clarify the project's governance structure, Prometheus joined the [Cloud Native Computing Foundation](https://cncf.io/) in 2016 as the second hosted project, after [Kubernetes](https://kubernetes.io/).

For more elaborate overviews of Prometheus, see the resources linked from the [media](/docs/introduction/media/) section.

### Features
Prometheus's main features are:

*   a multi-dimensional [data model](/docs/concepts/data_model/) with time series data identified by metric name and key/value pairs
*   PromQL, a [flexible query language](/docs/prometheus/latest/querying/basics/) to leverage this dimensionality
*   no reliance on distributed storage; single server nodes are autonomous
*   time series collection happens via a pull model over HTTP
*   [pushing time series](/docs/instrumenting/pushing/) is supported via an intermediary gateway
*   targets are discovered via service discovery or static configuration
*   multiple modes of graphing and dashboarding support
*   a multi-dimensional [data model](/docs/concepts/data_model/) with time series data identified by metric name and key/value pairs
*   PromQL, a [flexible query language](/docs/prometheus/latest/querying/basics/) to leverage this dimensionality
*   no reliance on distributed storage; single server nodes are autonomous
*   time series collection happens via a pull model over HTTP
*   [pushing time series](/docs/instrumenting/pushing/) is supported via an intermediary gateway
*   targets are discovered via service discovery or static configuration
*   multiple modes of graphing and dashboarding support

### Components

The Prometheus ecosystem consists of multiple components, many of which are optional:

*   the main [Prometheus server](https://github.com/prometheus/prometheus) which scrapes and stores time series data
*   [client libraries](/docs/instrumenting/clientlibs/) for instrumenting application code
*   a [push gateway](https://github.com/prometheus/pushgateway) for supporting short-lived jobs
*   special-purpose [exporters](/docs/instrumenting/exporters/) for services like HAProxy, StatsD, Graphite, etc.
*   an [alertmanager](https://github.com/prometheus/alertmanager) to handle alerts
*   various support tools