# This section will cover how to install 'Apache Webserver' and 'Nginx Webserver' on same virtual machine with two different port.

## In this scenario apache web server would be using the default port 80 and Nginx will be using port 8080.

###### We used google cloud for virtual machine using Centos 7. The below configurations were used on google cloud console for setting up:

a. Operating System Selection:
CentOS 7 - x86_64 built on 20190116.

b. Hard Disk for that particular VM:
Standard Persistent disk - 10 GB.

c. Firewall Access:

Allow HTTP traffic
Allow HTTPS traffic

Once the VM is created, we can now login this machine. In order to access the newly created VM from a root user we can use the following command:

sudo su

We now need to install Apache webserver, for this we can use 'yum' to install Apache through CentOS's default software repositories.

yum install httpd

systemctl enable httpd.service

enable Apache as a CentOS service so that it will automatically start after a reboot.

systemctl restart httpd

Using the above command will start the apache webservices. We can now directly use the public IP of this VM and test the apache web server is up and running.

Once this is tested successfully, can can add our own text inside the index.html file. This file needs to be created on /etc/www/html/.

Inside this file, we can add the text we wish to write. Restart the apache services and we can now see the new text on the web browser.

For apache there is nothing to be updated inside httpd.conf file, path: /etc/httpd/conf.