# Base Image 
FROM ubuntu:noble

# Owner of the image 
MAINTAINER Amit Vashistha <amitvashist.tech@gmail.com>

# APT Repo Update 
RUN apt-get  update 

# Install Apache2 Packages From APT Default Repos. 
RUN apt-get install apache2 -y 

## Deploy Custom WebPage
COPY info.html /var/www/html/info.html

# Excute the Sevice 
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
