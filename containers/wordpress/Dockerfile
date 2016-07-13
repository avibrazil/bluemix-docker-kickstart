FROM centos:6
MAINTAINER Avi Alkalay <avi at unix.sh>

# WordPress as RPM from https://avi.alkalay.net/2016/01/wordpress-fedora-rpm.html

ADD *.patch /tmp
COPY index.html /var/www/html/

RUN yum -y install epel-release;\
	yum -y install wordpress patch;\
	yum clean all;\
	sed -i '\
		         s/.localhost./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_HOSTNAME")/ ; \
		s/.database_name_here./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_NAME")/     ; \
		     s/.username_here./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_USERNAME")/ ; \
		     s/.password_here./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_PASSWORD")/ ; \
	' /etc/wordpress/wp-config.php;\
	cd /etc/httpd/conf.d; patch < /tmp/open-apache-server.patch;\
	cd /etc/httpd/conf;   patch < /tmp/disable-apache-logging.patch;\
	rm /tmp/*.patch




# Export port 80
EXPOSE 80

# This container is a web server serving PHP apps, so a plain Apache is our entry point
ENTRYPOINT [ "/usr/sbin/httpd", "-DFOREGROUND" ]



# Dockerfile by Avi Alkalay <avi at unix.sh> – https://Avi.Alkalay.net/
# Freely distributable