FROM python:3.8-slim-buster

LABEL maintainer="Jimmy chienfeng0719@hotmail.com"

ARG WORKDIR="app"
RUN apt-get update

# base packages
RUN apt-get install -y g++ gcc libxslt-dev screen vim tzdata bash wget curl git ansible
# kubectl
RUN curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"; chmod +x ./kubectl; mv ./kubectl /usr/local/bin/kubectl
# helm
RUN curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3; chmod 700 get_helm.sh; ./get_helm.sh;rm get_helm.sh
# kops
RUN curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64; chmod +x kops-linux-amd64; mv kops-linux-amd64 /usr/local/bin/kops

RUN mkdir -p ${WORKDIR}

ENV TZ=Asia/Taipei

WORKDIR ${WORKDIR}
