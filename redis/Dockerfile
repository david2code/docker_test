FROM ubuntu:20.04
MAINTAINER david david@example.com
ENV REFRESHED_AT 2020-1-1
RUN apt-get update
RUN apt-get install -y redis-server redis-tools
EXPOSE 6379
ENTRYPOINT ["/usr/bin/redis-server"]
CMD []