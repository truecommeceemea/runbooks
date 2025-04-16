# ElasticSearchHealth

## Meaning
The ElasticSearch cluster has unassigned shards.

## Impact
Services connected to the indicies could be down when the cluster status is red.

## Diagnosis
A yellow status means that the primary shard is allocated but replicas are not.
A red status indicates that the specific shards not allocated in the cluster.

Connect to either Kibana or the ElasticSearch nodesto see current status of the Elastic Search cluster.

```console
GET /_cluster/health/
```

## Mitigation
Make sure that all nodes are running and that the Elastic Search service is started.
