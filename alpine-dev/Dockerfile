ARG node_version
FROM node:${node_version}-alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY gitconfig /etc/gitconfig

ENV NODE_ENV=development
ENV PATH=$PATH:/root/.pulumi/bin
RUN apk add --no-cache aws-cli curl git libcap libc6-compat vault shellcheck shfmt
# https://github.com/hashicorp/vault/issues/10048#issuecomment-706315167
RUN setcap cap_ipc_lock= /usr/sbin/vault
RUN curl -fsSL https://get.pulumi.com/ | sh
