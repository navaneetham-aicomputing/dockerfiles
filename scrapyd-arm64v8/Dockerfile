FROM arm64v8/alpine:3.7

LABEL maintainer="Philipp Michalski <mail@phalski.com>" version="latest"

RUN apk add --no-cache python3 libxml2 libxslt py3-lxml openssl mariadb-client-libs \
  && apk add --no-cache --virtual build-dependencies alpine-sdk python3-dev libxslt-dev libxml2-dev libffi-dev mariadb-dev \
  && python3 -m ensurepip \
  && pip3 install --no-cache-dir --upgrade pip setuptools \
  && pip3 install --no-cache-dir scrapy scrapyd pymongo \
  && apk del build-dependencies \
  && rm -rf /root/.cache

COPY ./scrapyd.conf /etc/scrapyd/

VOLUME [ "/etc/scrapyd/", "/var/lib/scrapyd/" ]

EXPOSE 6800

ENTRYPOINT [ "scrapyd" ]
