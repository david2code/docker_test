FROM ubuntu:20.04
MAINTAINER david david@example.com
ENV REFRESHED_AT 2022-04-23

RUN apt-get update
RUN apt-get -y install ruby ruby-dev build-essential redis-tools
RUN gem install  sinatra json redis

RUN mkdir -p /opt/webapp

EXPOSE 4567

CMD [ "/opt/webapp/bin/webapp" ]