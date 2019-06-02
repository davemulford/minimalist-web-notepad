FROM docker.io/alpine

RUN apk add --no-cache apache2 php7-apache2 git curl socat
RUN rm /var/www/localhost/htdocs/index.html
RUN git clone https://github.com/davemulford/minimalist-web-notepad.git /var/www/localhost/htdocs
RUN chown -R apache:apache /var/www/localhost/htdocs

COPY webnotes.conf /etc/apache2/conf.d/webnotes.conf

#HEALTHCHECK --interval=1m --timeout=10s --retries=3 \
#  CMD echo /dev/null | socat tcp:localhost:9000 -

CMD ["/usr/sbin/httpd", "-DFOREGROUND"]
