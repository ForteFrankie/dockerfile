FROM debian:bullseye-slim

RUN set -ex \
    && apt-get update \
    && apt-get install -y --no-install-recommends openssh-server busybox dumb-init \
    && rm -rf /var/lib/apt/lists/*

EXPOSE 22/tcp

ADD entrypoint.sh /usr/local/bin/
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
CMD ["/usr/sbin/sshd", "-D", "-e"]
