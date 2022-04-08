ARG cypress_version
FROM cypress/browsers:${cypress_version}
RUN apk add --no-cache aws-cli curl git libc6-compat vault libcap
# https://github.com/hashicorp/vault/issues/10048#issuecomment-706315167
RUN setcap cap_ipc_lock= /usr/sbin/vault