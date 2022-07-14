FROM registry.access.redhat.com/ubi8/ubi

RUN curl -L https://github.com/mayurwaghmode/jq/releases/download/jq-1.6/jq-ppc64le -o /usr/bin/jq && chmod +x /usr/bin/jq
RUN curl -L https://github.com/mikefarah/yq/releases/download/v4.25.3/yq_linux_ppc64le -o /usr/bin/yq && chmod +x /usr/bin/yq 
RUN curl -L https://mirror.openshift.com/pub/openshift-v4/ppc64le/clients/ocp/latest-4.9/openshift-client-linux.tar.gz | tar -xz -C /usr/bin/
RUN curl -L https://github.com/sigstore/cosign/releases/download/v1.9.0/cosign-linux-ppc64le -o /usr/bin/cosign && chmod +x /usr/bin/cosign
RUN curl -L https://mirror.openshift.com/pub/openshift-v4/clients/pipeline/0.23.1/tkn-linux-ppc64le-0.23.1.tar.gz | tar -xz --no-same-owner -C /usr/bin/
RUN curl -L https://github.com/sigstore/rekor/releases/download/v0.9.1/rekor-cli-linux-ppc64le -o /usr/bin/rekor-cli && chmod +x /usr/bin/rekor-cli
RUN curl -L https://github.com/open-policy-agent/conftest/releases/download/v0.33.1/conftest_0.33.1_Linux_ppc64le.tar.gz | tar -xz --no-same-owner -C /usr/bin
RUN curl -L https://github.com/hacbs-contract/ec-cli/releases/download/snapshot/ec_linux_ppc64le -o /usr/bin/ec && chmod +x /usr/bin/ec

RUN dnf -y --setopt=tsflags=nodocs install \
    git \
    https://github.com/tektoncd/cli/releases/download/v0.24.0/tektoncd-cli-0.24.0_Linux-ppc64le.rpm \
    && dnf clean all

COPY util-scripts /appstudio-utils/util-scripts
