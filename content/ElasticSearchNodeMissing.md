# ElasticSearchNodeMissing

## Meaning
The ElasticSearch cluster has unavailable nodes.

## Impact
Elasticsearch might fail some queries, or unavailable.

## Diagnosis

Nodes being unavailable can be caused by different reasons like:

- Full disk on single-node deployment
- Full disk on multiple-nodes deployment
- JVM heap usage exceeds the allowed threshold on master nodes
- CPU usage exceeds the allowed threshold on master nodes
- Some nodes are unavailable and are displayed as missing

Consult the elasticsearch documentation

## Mitigation
Make sure that all nodes are running and that the Elastic Search service is started.
