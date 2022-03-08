ARG node_version
FROM node:${node_version}-alpine
ENV NODE_ENV=development
ENV PATH=$PATH:/root/.pulumi/bin
RUN apk add --no-cache aws-cli curl git libc6-compat vault libcap
# https://github.com/hashicorp/vault/issues/10048#issuecomment-706315167
RUN setcap cap_ipc_lock= /usr/sbin/vault
RUN curl -fsSL https://get.pulumi.com/ | sh
