# ARG BASE_IMAGE=registry.redhat.io/rhel8/httpd-24-micro
ARG BASE_IMAGE=quay.io/fedora/httpd-24:latest
FROM ${BASE_IMAGE}

# add httpd configs
COPY httpd-cfg/ /etc/httpd/conf.d/

# add data sources
COPY data/ /var/www/html/

# basic verification for data
RUN sha256sum /var/www/html/.* >> /var/www/html/sha256sum

# The run script uses standard ways to run the application
CMD run-httpd