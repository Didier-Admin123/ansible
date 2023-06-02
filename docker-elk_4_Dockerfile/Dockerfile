# ElasticSearch Dockerfile
FROM docker.elastic.co/elasticsearch/elasticsearch:8.7.0
MAINTAINER Didier
#Configure Elasticsearch 
#VOLUME /usr/share/elasticsearch/config/certs
COPY elasticsearch.yml /usr/share/elasticsearch/config
COPY certs.bash /usr/share/elasticsearch/config/certs/gencerts.sh
USER root
RUN chmod -R 777 /usr/share/ && chown -R elasticsearch:elasticsearch /usr/share/
USER elasticsearch 
RUN /usr/share/elasticsearch/config/certs/gencerts.sh
RUN chown -R elasticsearch:elasticsearch /usr/share/elasticsearch
