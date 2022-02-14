# can-hedgehogs-fly

nothing interesting here, just testing in-line mermaid.


```mermaid
  graph TD;
      Logstash_client-->MSK;
      Logstash_client-->HAProxy-->Fluentbit-->MSK;
      MSK-->Logstash_ingest--> Elasticsearch;
```
