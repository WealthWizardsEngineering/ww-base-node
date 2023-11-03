ARG  node_version
FROM node:${node_version}

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY gitconfig /etc/gitconfig

ENV NODE_ENV=development
ENV PATH=$PATH:/root/.pulumi/bin
RUN wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg \
  && echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(. /etc/os-release; echo $VERSION_CODENAME) main" | tee /etc/apt/sources.list.d/hashicorp.list \
  && apt-get -y update \
  && apt-get -y install --no-install-recommends git libcap2-bin python3 python3-pip vault \
  && pip3 install --break-system-packages awscli \
  && wget -O- https://get.pulumi.com/ | sh \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
