FROM docker.io/centos/httpd
USER root
LABEL maintainer="Shang Gao"
# Debug utils
RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs install curl ping traceroute tcpdump && \
    yum clean all
RUN echo "Linux Container Web Server" > /var/www/html/index.html
EXPOSE 80
# ENTRYPOINT ["/usr/sbin/apachectl","-DFOREGROUND"]
# ENTRYPOINT ["/usr/sbin/httpd","-D","FOREGROUND"]
CMD ["/run-httpd.sh"]