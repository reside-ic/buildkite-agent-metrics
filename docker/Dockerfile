#!/usr/bin/env bash
set -ex
HERE=$(dirname $0)
PACKAGE_ROOT=$(realpath $HERE/..)
PACKAGE_ORG=reside
TAG_BUILDKITE_AGENT_METRICS="${PACKAGE_ORG}/buildkite-agent-metrics:latest"

function cleanup {
    echo "Cleaning up"
    rm -rf $PACKAGE_ROOT/buildkite-agent-metrics
}
trap cleanup EXIT

git clone https://github.com/buildkite/buildkite-agent-metrics.git

docker build \
       -t $TAG_BUILDKITE_AGENT_METRICS \
       -f buildkite-agent-metrics/Dockerfile
       $PACKAGE_ROOT