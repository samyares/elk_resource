ElasticSearch:
  -coordination -> smart load balancer for fetching data from master node - use in large cases (not required)
  -Ingest -> like logstash, preprocess data before saving on elastic db but inside elastic.
  * u can use resful API to access to elastic datanase
  * u can make love with X-Pack to have features like security, alerting, reporting, ml, and ... (important features are paid)
  * just JSON file can save on elastic
  -indices -> elastic organize data into indices. each index is a collection of JSON
  * you can set replica for each index
  - shard -> elastic split indices into shards for distribution across nodes in the cluster. for example, 400GB index split into 40Gb ten shards
  * u can set temp on each node in cluster and set replica on each temp. for nodes that have good storage speed set temp label "hot" and for another set "warm" 
  * for generating SSL cert and clustering check episode 6
  * important compose ENV
    - bootstrap.memory_lock=true / turn off Linux swap
    - OPENSEARCH_JAVA_OPTS=Xms512m -Xmx512m / set the size of Java heap - recommend haf of system RAM
    - nofile 65536 / sets a limit of open files for the elastic user

Logstash:
  pipeline file
    input
      * you can use "type" for filter naming
    filter
    output
      * u can use multi-host for load balancing
      * can export to file


 
