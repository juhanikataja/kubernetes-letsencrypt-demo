FROM fedora:24
MAINTAINER Seth Jennings <sethdjennings@gmail.com>

RUN dnf install certbot -y && dnf clean all
RUN mkdir -p /etc/letsencrypt /var/log/letsencrypt

COPY secret-patch-template.json /
COPY entrypoint.sh /

# Following two lines are for debugging purposes
RUN chmod 774 /entrypoint.sh 
RUN chmod 664 /secret-patch-template.json
RUN chmod 775 /var/log/letsencrypt /etc/letsencrypt

CMD ["/entrypoint.sh"]
