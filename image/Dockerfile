#FROM registry.redhat.io/ubi8/ubi
FROM registry.redhat.io/openshift4/ose-cli

# RUN curl --location \
#   https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz | \
#   tar xvfz - --directory /usr/local/bin

ARG TKN_VERSION=0.20.0
RUN ARCH=$(uname -m) && [ "$ARCH" == "amd64" ] && ARCH=64bit ; \
    rpm --install https://github.com/tektoncd/cli/releases/download/v$TKN_VERSION/tektoncd-cli-$TKN_VERSION_Linux-$ARCH.rpm