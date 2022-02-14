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
   Generator-->Logstash;
   Logstash-->Q1{Has this<br/>Environment Been<br/>Migrated};
   Q1-->Y1((Yes));
   Q1-->N1((No));
   N1-->Redis-->I1[Webops<br/>Ingest];
   I1-->P1;
   I1-->P2;
   I1-->P3;
   Y1-->Q2{Is this<br/>Webops?};
   Q2-->Y2((Yes));
   Q2-->N2((No));
   Y2-->P1;
   Y2-->P2;
   Y2-->P3;
   N2-->HAProxy-->Fluentbit;
   Fluentbit-->P1;
   Fluentbit-->P2;
   Fluentbit-->P3;
   I2[NWT<br/>Ingest];
   P1-->I2;
   P2-->I2;
   P3-->I2;
   I2-->S3;
   I2-->Elasticsearch;
```
