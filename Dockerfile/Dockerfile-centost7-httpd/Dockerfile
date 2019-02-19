FROM centos:centos7

LABEL "image-type"="huy-test"
MAINTAINER huytm

RUN yum update -y 
RUN yum install httpd -y

ENV source /var/www/html/

VOLUME ["/var/log/httpd"]

COPY index.html ${source}
COPY start.sh /start.sh

RUN chmod +x /start.sh
CMD ["/start.sh"]

EXPOSE 80
