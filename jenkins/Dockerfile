FROM ubuntu:20.04
MAINTAINER david@example.com
ENV REFRESHED_AT 2020-10-1

RUN apt-get update && apt-get install -y curl
RUN curl https://get.docker.io/gpg |apt-key add -
RUN echo deb https://get.docker.io/ubuntu docker main > /etc/apt/sources.list.d/docker.list
RUN apt-get update -qq && apt-get install -qqy iptables ca-certificates lxc openjdk-6-jdk git-core lxc-docker

ENV JENKINS_HOME /opt/jenkins/data
ENV JENJINS_MIRROR http://mirrors.jenkins-ci.org

RUN mkdir -p $JENKINS HOME/plugins
RUN curl -sf -o /opt/jenkins/jenkins.war -L $JENKINS_MIRROR/war-stable/latest/jenkins.war

RUN for plugin in chucknorris greenballs scm-api git-client git ws-cleanup;\
		do curl -sf -o $JENKINS_HOME/plugins/${plugin}.hpi \
		-L $JENKINS_MIRROR/plugins/${plugin}/latest/${plugin}.hpi; done

ADD ./dockerjenkins.sh /usr/local/bin/dockerjenkins.sh

VOLUME /var/lib/docker

EXPOSE 8080

ENTRYPOINT [ "/usr/local/bin/dockerjenkins.sh" ]