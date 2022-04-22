#FROM registry.redhat.io/ubi8/ubi
FROM registry.redhat.io/rhel8/go-toolset:1.14 AS builder

WORKDIR /opt/app-root/src/go/src/github.com/tektoncd/cli
USER root
COPY $REMOTE_SOURCE/app .
ARG RELEASE_VERSION=0.19.0

RUN make RELEASE_VERSION=${RELEASE_VERSION} bin/tkn

FROM registry.redhat.io/openshift4/ose-cli
# RUN curl --location \
#   https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz | \
#   tar xvfz - --directory /usr/local/bin
COPY --from=builder /opt/app-root/src/go/src/github.com/tektoncd/cli/bin/tkn /usr/local/bin

