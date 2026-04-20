FROM mikefarah/yq:4@sha256:0cb4a78491b6e62ee8a9bf4fbeacbd15b5013d19bc420591b05383a696315e60

# github action recommendation is to run as root.
# https://docs.github.com/en/actions/creating-actions/dockerfile-support-for-github-actions#user
USER root

RUN apk add --no-cache jq curl

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
