# Omeka Quickstart on OpenShift Express #
Omeka is a free, flexible, and open source web-publishing platform for the display of library, museum, archives, and scholarly collections and exhibitions.

## Installation ##

1. Create an account at http://openshift.redhat.com/

1. Install the [OpenShift Client Tools][rhc]

1. Create a PHP application on OpenShift

```
rhc app create -a omeka -t php-5.4
```

1. Add mysql support to your application

```
rhc cartridge add -a omeka -c mysql-5.1
```

1. Add this upstream Omeka quickstart repository

```
cd omeka
git remote add upstream -m master git://github.com/waynegraham/omeka-quickstart.git
git pull -s recursive -X theirs upstream master
```
1. Push the quickstart code to your Openshift application

```
git push
```

1. Visit appName-yourNamespace.rhcloud.com/install to setup your site!

### Adding Themes ###
You can find theme packages at http://omeka.org/add-ons/themes/
click on the theme image to make sure it will work with this version of Omeka.

[rhc]: https://developers.openshift.com/en/getting-started-client-tools.html
