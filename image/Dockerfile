FROM registry.access.redhat.com/ubi8
#FROM registry.redhat.io/openshift4/ose-cli

RUN ARCH=$(uname -m) && curl --location \
  https://mirror.openshift.com/pub/openshift-v4/${ARCH}/clients/ocp/stable/openshift-client-linux.tar.gz | \
  tar xvfz - --directory /usr/local/bin

ARG TKN_VERSION=0.33.0
RUN ARCH=$(uname -m) && [ "$ARCH" == "x86_64" ] && ARCH=64bit ; \
    rpm --install https://github.com/tektoncd/cli/releases/download/v${TKN_VERSION}/tektoncd-cli-${TKN_VERSION}_Linux-${ARCH}.rpm
