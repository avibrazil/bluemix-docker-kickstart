FROM centos:6
MAINTAINER Avi Alkalay <avi at unix.sh>


RUN yum -y install epel-release;\
	yum -y install wordpress;\
	yum clean all;\
	sed -i 's/Require local/Require all granted/' /etc/httpd/conf.d/wordpress.conf;\
	sed -i 's/database_name_here/${VCAP_SERVICES_CLEARDB_0_CREDENTIALS_NAME}/; s/username_here/${VCAP_SERVICES_CLEARDB_0_CREDENTIALS_USERNAME}/; s/password_here/${VCAP_SERVICES_CLEARDB_0_CREDENTIALS_PASSWORD}/; s/localhost/${VCAP_SERVICES_CLEARDB_0_CREDENTIALS_HOSTNAME}/' /etc/wordpress/wp-config.php




# Export port 80
EXPOSE 80

# This container is a web server serving PHP apps, so a plain Apache is our entry point
ENTRYPOINT [ "/usr/sbin/httpd", "-DFOREGROUND" ]
