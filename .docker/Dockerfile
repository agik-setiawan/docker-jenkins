FROM 'jenkins/jenkins:lts'

USER root
RUN apt-get update -qq \
    && apt-get install -qqy \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN apt-key fingerprint 0EBFCD88
RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
RUN apt-get update -qq && apt-get install docker-ce docker-ce-cli containerd.io -y
RUN usermod -aG docker jenkins

