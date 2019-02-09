ARG BUILD_FROM=hassioaddons/base:2.3.1
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Add env
ENV LANG="C.UTF-8" \
    TERM="xterm-256color"

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Setup base
# hadolint ignore=DL4001
ARG BUILD_ARCH

# Copy root filesystem
COPY rootfs /

# Build arguments
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

ADD https://storage.googleapis.com/hassdns-artifacts/hassdns-${BUILD_VERSION}-${BUILD_ARCH} /usr/bin/hassdns
RUN chmod +x /usr/bin/hassdns

# Labels
LABEL \
    io.hass.name="HassDNS" \
    io.hass.description="Home Assistant DNS service" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Lars Larsson <lars.la@gmail.com>" \
    org.label-schema.description="Home Assistant DNS service" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="HassDNS" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.url="https://github.com/larsla/hassdns" \
    org.label-schema.usage="https://github.com/larsla/hassio-addons/tree/master/hassdns/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/larsla/hassdns" \
    org.label-schema.vendor="larsla's Hass.io Add-ons"