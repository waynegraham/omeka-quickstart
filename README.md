 omeka-quickstart

 Quickstart Omeka 2.0 on OpenShift Express. Omeka is a free, flexible, and open source web-publishing platform for the display of library, museum, archives, and scholarly collections and exhibitions.

 INSTALLATION

 1) Create an account at http://openshift.redhat.com/
 
 2) Create a PHP application
     $ rhc app create -a omeka -t php-5.3

 3) Add mysql support to your application
     $ rhc cartridge add -a omeka -c mysql-5.1

 4) Add this upstream Omeka 2.0 quickstart repository
     $ cd omeka
     $ git remote add upstream -m master git://github.com/loudWhale/omeka-quickstart.git
     $ git pull -s recursive -X theirs upstream master

 5) Push the quickstart code to your Openshift application
     $ git push

 6) Start using your Omeka 2.0 application!
     Default Admin username: Administrator
     Default Admin password: OpenShiftAdmin
