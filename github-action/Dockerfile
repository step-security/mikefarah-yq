FROM mikefarah/yq:4@sha256:603ebff15eb308a05f1c5b8b7613179cad859aed3ec9fdd04f2ef5d32345950e

# github action recommendation is to run as root.
# https://docs.github.com/en/actions/creating-actions/dockerfile-support-for-github-actions#user
USER root

RUN apk add --no-cache jq curl

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
