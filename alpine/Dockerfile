FROM alpine:3.18.3 as build
LABEL maintainer="fengjx<https://github.com/fengjx>"

RUN apk add --update linux-headers alpine-sdk perl
RUN cd /tmp                               && \
    git clone -b 4.2.0 https://github.com/wg/wrk
RUN cd /tmp/wrk                           && \
    make

FROM alpine:3.18.3
COPY --from=build /tmp/wrk/wrk /usr/local/bin/
RUN apk add --no-cache libgcc
WORKDIR /data
ENTRYPOINT ["wrk"]