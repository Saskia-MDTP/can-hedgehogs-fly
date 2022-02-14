# can-hedgehogs-fly

nothing interesting here, just testing in-line mermaid.


```mermaid
  graph TD;
      "Logstash client"-->MSK;
      "Logstash client"-->HAProxy-->Fluentbit-->MSK;
      MSK-->"Logstash ingest"--> Elasticsearch;
```
