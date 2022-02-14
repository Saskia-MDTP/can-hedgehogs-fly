# can-hedgehogs-fly

nothing interesting here, just testing in-line mermaid.


```mermaid
  graph LR;
      Nginx-->Docker-->LC[Logstash client]-.->MSK;
      LC[Logstash client]-->HAProxy-->Fluentbit-->MSK;
      MSK-->LI[Logstash ingest]--> Elasticsearch;
```
