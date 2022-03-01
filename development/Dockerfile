ARG node_version
FROM node:${node_version}-alpine
ENV NODE_ENV=development
ENV PATH=$PATH:/root/.pulumi/bin
RUN apk add --no-cache aws-cli curl git libc6-compat \
 && curl -fsSL https://get.pulumi.com/ | sh
