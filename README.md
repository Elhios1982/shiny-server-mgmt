# shiny-server-mgmt
https://docs.rstudio.com/shiny-server/

## Starting and Stopping the server
$ sudo systemctl start shiny-server
$ sudo systemctl stop shiny-server

OR

$ sudo stop shiny-server
$ sudo start shiny-server



## Once server has started, we need to add port 3838 to firewall to be able to access
### list port and services added to the firewall
$ sudo firewall-cmd --list-all

### If port 3838 not there, it needs to be added
$ sudo firewall-cmd -add-port=3838/tcp --permanent
$ sudo firewall-cmd --reload

### Verify it was added successfully
$ sudo firewall-cmd --list-all

sudo firewall-cmd --state
sudo systemctl stop firewalld
sudo systemctl start firewalld

### if shiny server is running on VM @ virtualbox we need to use Network = Bridged

### Install 'rmarkdown' package using
sudo su - \
-c "R -e \"install.packages('rmarkdown', repos='https://cran.rstudio.com/')\""

### This should be it to have Shiny server up and running, log file can be checked here
$ vim /var/log/shiny-server.log


