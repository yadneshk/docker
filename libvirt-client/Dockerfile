FROM alpine:latest
RUN apk add --no-cache libvirt-client && \
    apk add --no-cache openssh
ENTRYPOINT [ "virsh","--connect" ]
