FROM httpd:alpine

RUN sed -i '/LoadModule rewrite_module/s/^#//g' /usr/local/apache2/conf/httpd.conf

RUN echo "Include /usr/local/apache2/sites-enabled/" >> /usr/local/apache2/conf/httpd.conf

RUN echo "apachectl -S"