FROM centos:6
MAINTAINER Avi Alkalay <avi at unix.sh>

# WordPress as RPM from https://avi.alkalay.net/2016/01/wordpress-fedora-rpm.html

ADD wordpress.conf.patch /tmp

RUN yum -y install epel-release;\
	yum -y install wordpress patch;\
	yum clean all;\
	sed -i          's/.localhost./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_HOSTNAME")/' /etc/wordpress/wp-config.php;\
	sed -i 's/.database_name_here./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_NAME")/'     /etc/wordpress/wp-config.php;\
	sed -i      's/.username_here./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_USERNAME")/' /etc/wordpress/wp-config.php;\
	sed -i      's/.password_here./getenv("VCAP_SERVICES_CLEARDB_0_CREDENTIALS_PASSWORD")/' /etc/wordpress/wp-config.php;\
	cd /etc/httpd/conf.d; patch < /tmp/wordpress.conf.patch;\
	rm /tmp/wordpress.conf.patch




# Export port 80
EXPOSE 80

# This container is a web server serving PHP apps, so a plain Apache is our entry point
ENTRYPOINT [ "/usr/sbin/httpd", "-DFOREGROUND" ]
