# In this section we will explain how to setup a load balancer between two nodes on google cloud.

## We will be using 'haproxy' load balancer.

we can now login to the machine where we want to intall haproxy. In order to access the newly created VM from a root user we can use the following command

``` sudo su ```

Execute the below command in order to install haproxy.

``` yum install haproxy ```

Once haproxy is installed, we need to enable haproxy services:

``` systemctl enable haproxy ```

Now execute the below command in order to start haproxy services:

``` systemctl start haproxy ```

The services should be start, we can confirm this by executing the below command: 

``` systemctl status haproxy ```

###### We now need to update the haproxy.cfg file in order for the load balancer to work properly.

###### Note: We are using the same VMs that were used earlier to install apache and nginx. Below is the link for the setup, haproxy will be using these two VM to create a cluster of two nodes.

https://github.com/mfaquih/Setting-up-Web-Servers/blob/master/README.md

Now go the following path: ``` /etc/haproxy/ ``` and update ``` haproxy.cfg ``` for the default setting. 

