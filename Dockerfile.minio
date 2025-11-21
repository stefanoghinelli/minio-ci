FROM alpine:3.20

ARG TARGETARCH
ARG RELEASE

RUN apk add --no-cache ca-certificates

COPY minio-${TARGETARCH}.${RELEASE} /usr/bin/minio
COPY minio-${TARGETARCH}.${RELEASE}.minisig /usr/bin/minio.minisig
COPY minio-${TARGETARCH}.${RELEASE}.sha256sum /usr/bin/minio.sha256sum
COPY dockerscripts/docker-entrypoint.sh /usr/bin/docker-entrypoint.sh

RUN chmod +x /usr/bin/minio /usr/bin/docker-entrypoint.sh

ENV MINIO_UPDATE_MINISIGN_PUBKEY="RWTx5Zr1tiHQLwG9keckT0c45M3AGeHD6IvimQHpyRywVWGbP1aVSGav" \
    MINIO_CONFIG_ENV_FILE=config.env

EXPOSE 9000 9001

ENTRYPOINT ["/usr/bin/docker-entrypoint.sh"]
VOLUME ["/data"]
CMD ["minio"]
