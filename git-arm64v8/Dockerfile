FROM arm64v8/alpine:3.7

LABEL maintainer="Philipp Michalski <mail@phalski.com>" version="latest"

RUN apk --no-cache add git

VOLUME [ "/git" ]
WORKDIR /git

ENTRYPOINT [ "git" ]
CMD [ "--help" ]