ARG cypress_version
FROM cypress/browsers:${cypress_version}

# Needed to add the hashicorp repo
RUN apt-get update && \
    apt-get install -y \
    lsb-base \
    lsb-release \
    gnupg2 \
    software-properties-common

# Needed to get vault from hashicorp
RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add - && \
    apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

RUN apt-get update && \
    apt-get install -y \
    vault