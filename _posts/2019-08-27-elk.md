---
title:  ELK (Elasticsearch，Logstash和Kibana)
---

###  [ELK是什么](https://www.elastic.co/cn/what-is/elk-stack) 
“ELK”是三个开源项目的首字母缩写：Elasticsearch，Logstash和Kibana。Elasticsearch是一个搜索和分析引擎。Logstash是一个服务器端数据处理管道，它同时从多个源中提取数据，对其进行转换，然后将其发送到像Elasticsearch这样的“存储”。Kibana允许用户使用Elasticsearch中的图表和图形来可视化数据。   
![](https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt745c7c0288922a62/5c11edccdf09df047814db29/elk-stack-3-elks-stacked.svg)          
--- 

###  [ELK安装](https://www.elastic.co/cn/start)
- [Elasticsearchan安装启动](https://www.elastic.co/guide/en/elasticsearch/reference/7.3/docker.html#docker) (docker方式)   
   - 下载image
```        
    docker pull docker.elastic.co/elasticsearch/elasticsearch:7.3.1
```   
   - 启动docker
```        
    docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.3.1
```   
- **Logstash安装启动**
   - 下载image
```        
    docker pull docker.elastic.co/elasticsearch/elasticsearch:7.3.1
```   
   - 启动docker
```        
    docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.3.1
```   

- [Kibana安装启动](https://www.elastic.co/guide/en/kibana/current/docker.html)
   - 下载image
```        
    docker pull docker.elastic.co/kibana/kibana:7.3.1
```   
   - 启动docker
```        
    docker run --link YOUR_ELASTICSEARCH_CONTAINER_NAME_OR_ID:elasticsearch -p 5601:5601 {docker-repo}:{version}
```   
- [Filebeat](https://www.elastic.co/guide/en/beats/filebeat/7.3/filebeat-getting-started.html)

```     
``` 
---
