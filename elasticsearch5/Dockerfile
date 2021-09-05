FROM elasticsearch:5.6.5

MAINTAINER NguyenQuocDai <quocdaijr@gmail.com>

ENV ES_JAVA_OPTS="-Xms512m -Xms512m"
ENV MAX_OPEN_FILES=262144
ENV MAX_LOCKED_MEMORY=unlimited

RUN mkdir /etc/sysctl.d

RUN echo "* - nofile 262144" >> /etc/security/limits.conf && \
    echo "* - memlock 262144" >> /etc/security/limits.conf && \
    echo vm.max_map_count=262144 > /etc/sysctl.d/max_map_count.conf && \
    echo vm.swappiness=0 > /etc/sysctl.d/swappiness.conf

ADD ./config/elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml

ADD ./plugins/analysis-icu-5.6.5.zip /tmp/analysis-icu-5.6.5.zip
RUN bin/elasticsearch-plugin install file:///tmp/analysis-icu-5.6.5.zip

ADD ./plugins/elasticsearch-analysis-vietnamese-5.6.5.zip /tmp/elasticsearch-analysis-vietnamese-5.6.5.zip
RUN bin/elasticsearch-plugin install file:///tmp/elasticsearch-analysis-vietnamese-5.6.5.zip

#RUN bin/elasticsearch-plugin install -b x-pack

RUN cp /usr/share/zoneinfo/Asia/Ho_Chi_Minh /etc/localtime


EXPOSE 9200 9300

# CMD ["elasticsearch"]