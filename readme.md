# ApacheManage

A better way to manage Apache virtual host configurations on RedHat/CentOS.

The standard Ubuntu installation of Apache uses individual files for each virtual host stored in the /etc/apache2/sites-available directory. Those virtual hosts that should be active are then symlinked into the /etc/apache2/sites-enabled directory. The process of creating/destroying the symlinks is handled by scripts, _a2ensite_ and _a2dissite_, which enable and disable the virtual host configurations respectively.

The standard RedHat/CentOS installation of Apache is configured to specify all virtual hosts in the main httpd.conf file which can be rather ugly to manage. Thus, this product borrows all the good management techniques from the Ubuntu install and implements them under a fresh RedHat/CentOS installation.


## Installation

* append text and include statement to the end of /etc/httpd/conf/httpd.conf
* replace contents of /etc/httpd/conf.d/vhosts.conf with documentation if it exists
* cd /etc/httpd
* sudo mkdir sites-enabled sites-available
* cd /usr/local
* sudo mkdir -p scripts/apachemanage
* sudo yum install hg
* cd /usr/local/scripts/apachemanage
* sudo hg clone https://paulrentschler@bitbucket.org/paulrentschler/apachemanage ./
* sudo ln -s /usr/local/scripts/apachemanage/a2manage /usr/sbin/a2ensite
* sudo ln -s /usr/local/scripts/apachemanage/a2manage /usr/sbin/a2dissite


## Future improvements

* Look at adding a shell script that takes cares care of most of the steps under _Installation_.
* Fix the use of environment variables in the a2manage script so that the Apache path isn't hard coded.
* Add a copy of the Apache license to this project.

