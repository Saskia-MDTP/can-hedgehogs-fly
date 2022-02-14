# can-hedgehogs-fly

nothing interesting here, just testing in-line mermaid.


```mermaid
  graph LR;
      Nginx-->Docker-->LC[Logstash client]
      LC-->E{Is this<br/>Webops?}--Yes-->MSK;
      E--No-->HAProxy-->Fluentbit-->MSK;
      MSK-->LI[Logstash ingest]--> Elasticsearch;
```


```mermaid
  graph LR;
      subgraph MSK
          subgraph Broker_1
              P1[Logs Topic<br/>Part 1];
           end
          subgraph Broker_2
              P2[Logs Topic<br/>Part 2];
           end
          subgraph Broker_3
              P3[Logs Topic<br/>Part 3];
           end
       end
       Logstash-->P1;
       Logstash-->P2;
       Logstash-->P3;
       Logstash-->HAProxy-->Fluentbit;
       Fluentbit-->P1;
       Fluentbit-->P2;
       Fluentbit-->P3;
```
