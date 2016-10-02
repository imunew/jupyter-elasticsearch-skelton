FROM elasticsearch:2.3

RUN apt-get update

RUN ./bin/plugin install lmenezes/elasticsearch-kopf/v2.1.1
RUN ./bin/plugin install mobz/elasticsearch-head
RUN ./bin/plugin install org.codelibs/elasticsearch-analyze-api/2.3.0

RUN ./bin/plugin install analysis-kuromoji
RUN ./bin/plugin install analysis-icu
RUN ./bin/plugin install org.codelibs/elasticsearch-analysis-synonym/2.3.0 -b
RUN ./bin/plugin install org.codelibs/elasticsearch-analysis-ja/2.3.0 -b
RUN ./bin/plugin install org.codelibs/elasticsearch-analysis-kuromoji-neologd/2.3.0 -b

RUN mkdir -p /var/elasticsearch/snapshot && \
    chown -R elasticsearch:elasticsearch /var/elasticsearch

ADD config/elasticsearch.yml /usr/share/elasticsearch/config/
