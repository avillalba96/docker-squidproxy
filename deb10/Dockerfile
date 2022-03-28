FROM debian:10.5
LABEL maintainer="example@example.com"

ENV SQUID_VERSION=4.6-1+deb10u6 \
    SQUID_CACHE_DIR=/var/spool/squid \
    SQUID_LOG_DIR=/var/log/squid \
    SQUID_USER=proxy

RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive apt-get install -y squid=${SQUID_VERSION}* ldap-utils ca-certificates squid-langpack squid-purge vim rsyslog procps\
 && rm -rf /var/lib/apt/lists/*

VOLUME ["/etc/squid"]

EXPOSE 3128/tcp

# Editando logrotate
COPY logrorate_squid.conf /etc/logrotate.d/squid
RUN chown root.root /etc/logrotate.d/squid
RUN chmod 0644 /etc/logrotate.d/squid

#Copy and run install script
COPY entrypoint.sh /opt/
RUN chmod +x /opt/entrypoint.sh
ENTRYPOINT ["/opt/entrypoint.sh"]
