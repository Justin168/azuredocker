FROM simonhutson/centos-7.2
MAINTAINER Simon Hutson

# Install the latest versions of PHP and Apache HTTP Server
RUN \
yum -y update && \
yum -y install php php-common php-cli php-mysql php-gd php-mbstring httpd && \
yum clean all && \
rm -fr /var/cache/*

COPY docker-entrypoint.sh /entrypoint.sh
RUN chmod -v +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
CMD ["httpd", "-DFOREGROUND"]

EXPOSE 80
