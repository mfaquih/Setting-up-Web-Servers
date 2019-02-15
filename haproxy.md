# In this section we will explain how to setup a load balancer between two nodes on google cloud.

## We will be using 'haproxy' load balancer.

we can now login to the machine where we want to intall haproxy. In order to access the newly created VM from a root user we can use the following command

``` sudo su ```

Execute the below command in order to install haproxy.

``` yum install haproxy ```

Once haproxy is installed, we need to enable haproxy services:

``` systemctl enable haproxy ```

Now execute the below command in order to start haproxy services:

``` systemctl start haproxy ``

The services should be start, we can confirm this by executing the below command: 

``` systemctl status haproxy ``
