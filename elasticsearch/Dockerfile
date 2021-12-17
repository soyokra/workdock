ARG ELK_VERSION=7.5.1
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}
# RUN sysctl -w vm.max_map_count=262144
RUN cd /usr/share/elasticsearch/plugins && mkdir ik
ADD ./plugins/elasticsearch-analysis-ik-7.5.1.zip /usr/share/elasticsearch/plugins/ik
EXPOSE 9200 9300
