FROM centos
MAINTAINER Avi Alkalay <avi at unix.sh>


RUN yum -y install epel-release;\
	yum -y install nginx;\
	yum clean all


COPY index.php /var/www/html/

# Export port 80
EXPOSE 80

# This container is a web server serving PHP apps, so a plain Apache is our entry point
ENTRYPOINT [ "/usr/sbin/nginx" ]
