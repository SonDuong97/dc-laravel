ARG HTTPD_SON_VERSION=2

FROM httpd:${HTTPD_SON_VERSION}

RUN apt-get update -y\
	&& apt-get install htop\
	&& echo "heelo ${HTTPD_SON_VERSION}"

ADD ./httpd.conf /usr/local/apache2/conf/httpd.conf
ADD ./httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf

EXPOSE 80 433

CMD ["httpd-foreground"]