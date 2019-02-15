# This section will cover how to install 'Apache Webserver' and 'Nginx Webserver' on same virtual machine with two different port.

## In this scenario apache web server would be using the default port 80 and Nginx will be using port 8080.

###### We used google cloud for virtual machine using Centos 7. The below configurations were used on google cloud console for setting up:

- Operating System Selection:
CentOS 7 - x86_64 built on 20190116.

- Hard Disk for that particular VM:
Standard Persistent disk - 10 GB.

- Firewall Access:
1. Allow HTTP traffic
2. Allow HTTPS traffic

Once the VM is created, we can now login to this machine. In order to access the newly created VM from a root user we can use the following command:

``` sudo su ```

We now need to install Apache webserver, for this we can use 'yum' to install Apache through CentOS's default software repositories.

``` yum install httpd ```

``` systemctl enable httpd.service ```

Enable Apache as a CentOS service so that it will automatically start after a reboot.

``` systemctl restart httpd ```

Using the above command will start the apache webservices. We can now directly use the public IP of this VM and test the apache web server is up and running.

We can also use the below command and the status for apache web server.

``` systemctl status httpd ```

Once this is tested successfully, can can add our own text inside the index.html file. This file needs to be created on /etc/www/html/.

Path: ``` /var/www/html/index.html ```

Inside this file, we can add the text we wish to see on the web page. Restart the apache services and we can now see the new text on the web browser.

Also note that for apache there is NOTHING to be updated inside ``` httpd.conf ``` file as it runs on the default port : 80.

Path: ``` /etc/httpd/conf/httpd.conf ```

###### As we need to create a cluster between two nodes, we will now create one more VM using google clould. Please following the same steps for second node. 

## Once we have configured Apache on both nodes we now need to install NGINX on the same virtual machine, we can do this by following the below steps:

Go to the VM where now we want to install NGINX. We can use the below command if we want to access the newly created VM from a root user:

``` sudo su ```

We now need to install Apache webserver, for this we can use 'yum' to install Apache through CentOS's default software repositories.

``` yum install nginx ```

``` systemctl enable nginx.conf ```

Enable Apache as a CentOS service so that it will automatically start after a reboot.

``` systemctl restart nginx ```

We can also use the below command and the status for Nginx web server.

``` systemctl status nginx ```

###### Please note that nginx web server will be busted and the status shown will be failed, this is due to both apache and nginx are running on the same webserver.

In order to fix this problem we need to point nginx to a different port. This can be achived by update nginx configuration file to a different port. As for apache we are using port 80, for nginx we can use port 8080.



