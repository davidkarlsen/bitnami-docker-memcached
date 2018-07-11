FROM bitnami/oraclelinux-extras:7-r30
LABEL maintainer "Bitnami <containers@bitnami.com>"

ENV BITNAMI_PKG_CHMOD="-R g+rwX" \
    HOME="/"

# Install required system packages and dependencies
RUN install_packages cyrus-sasl-lib glibc keyutils-libs krb5-libs libcom_err libevent libselinux nss-softokn-freebl pcre
RUN bitnami-pkg unpack memcached-1.5.9-0 --checksum 9fbefebbbd4fde688b6b7de3f15731143ca4aaf93c5147e990af806287560dd9

COPY rootfs /
ENV BITNAMI_APP_NAME="memcached" \
    BITNAMI_IMAGE_VERSION="1.5.9-ol-7-r2" \
    MEMCACHED_CACHE_SIZE="64" \
    MEMCACHED_PASSWORD="" \
    MEMCACHED_USERNAME="root" \
    PATH="/opt/bitnami/memcached/bin:$PATH"

EXPOSE 11211

USER 1001
ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["/run.sh"]