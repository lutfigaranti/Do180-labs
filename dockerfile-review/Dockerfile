FROM ubi7/ubi:7.7

MAINTAINER username <username@example.com>

ENV PORT 8080

RUN yum install -y httpd

RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
    chown -R apache:apache /etc/httpd/logs/ && \
    chown -R apache:apache /run/httpd/

USER apache
EXPOSE ${PORT}
COPY ./src/ /var/www/html/
CMD ["httpd", "-D", "FOREGROUND"]

# Expose the custom port that you provided in the ENV var

# Copy all files under src/ folder to Apache DocumentRoot (/var/www/html) 

# Start Apache in the foreground
