ARG cypress_version
FROM cypress/${cypress_version}

# Needed to add the hashicorp repo
RUN apt-get update && \
    apt-get install -y \
    lsb-base \
    lsb-release \
    gnupg2 \
    software-properties-common \
    git \
    curl

# Needed to get vault from hashicorp
RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add - && \
    apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

RUN apt-get update && \
    apt-get install -y \
    vault && \
    setcap -r $(which vault) && \
    vault -v

# Build Add PlayWright WebKit browser
RUN npx playwright install --with-deps webkit

# https://github.com/hashicorp/vault/issues/10048#issuecomment-706315167
RUN setcap cap_ipc_lock= /usr/bin/vault