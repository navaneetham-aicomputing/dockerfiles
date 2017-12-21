FROM arm64v8/alpine:3.7

LABEL maintainer="Philipp Michalski <mail@phalski.com>" version="latest"

RUN apk add --no-cache python3 libxml2 libxslt py3-lxml openssl \
  && apk add --no-cache --virtual build-dependencies alpine-sdk libxslt-dev libxml2-dev libffi-dev python3-dev \
  openssl-dev \
  && python3 -m ensurepip \
  && pip3 install --no-cache-dir --upgrade pip setuptools \
  && pip3 install --no-cache-dir scrapy scrapyd \
  && apk del build-dependencies \
  && rm -rf /root/.cache

COPY ./scrapyd.conf /etc/scrapyd/

VOLUME [ "/etc/scrapyd/", "/var/lib/scrapyd/" ]

EXPOSE 6800

ENTRYPOINT [ "scrapyd" ]
