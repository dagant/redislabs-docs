---
Title: Benchmarking Redis Enterprise
description: 
weight: 50
alwaysopen: false
---
If you need to do a quick performance benchmark of Redis Enterprise, we
have a tool just for this; memtier\_benchmark.

Prerequisites:

-   Redis Enterprise Software installed
-   A cluster configured
-   A database created

If you need a quick setup for the prerequisites, please [go
here]({{< relref "/rs/getting-started/quick-setup.md" >}}).

It is recommended to run memtier\_benchmark on a separate node that is
not part of the cluster being tested. If you run it on a node of the
cluster, be mindful that it will affect the performance of both the
cluster and memtier\_benchmark.

``` {style="border: 2px solid #ddd; background-color: #333; color: #fff; padding: 10px; -webkit-font-smoothing: auto;"}
$ /opt/redislabs/bin/memtier_benchmark -s $DB_HOST -p $DB_PORT \
-t 4 -R --ratio=1:1
```

This command instructs memtier\_benchmark to connect to your Redis
Enterprise database and generates a load doing the following:

-   A 50/50 Set to Get ratio
-   Each object will have random data in the value

## Populate a Database with Testing Data

If you need to populate a database with some test data for a proof of
concept, or failover testing, etc. here is an example for you.

``` {style="border: 2px solid #ddd; background-color: #333; color: #fff; padding: 10px; -webkit-font-smoothing: auto;"}
$ memtier_benchmark -s $DB_HOST -p $DB_PORT -R -n allkeys \
-d 500 --key-pattern=P:P --ratio=1:0
```

This command instructs memtier\_benchmark to connect to your Redis
Enterprise database and generates a load doing the following:

-   Write objects only, no reads
-   A 500 byte object
-   Each object will have random data in the value
-   Each key will have a random pattern, then a colon, followed by a
    random pattern.

Run this command until it fills up your database to where you want it
for testing. The easiest way to check is on the database metrics page.

![](/images/rs/memtier_metrics_page.png?width=700&height=158)

Another use for memtier\_benchmark is to populate a database with data
for failure testing.
