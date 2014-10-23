# Omeka Quickstart on OpenShift Express
Omeka is a free, flexible, and open source web-publishing platform for the display of library, museum, archives, and scholarly collections and exhibitions.

## Installation

* Create an account at http://openshift.redhat.com/

* Install the [OpenShift Client Tools][rhc]

* Create a PHP application on OpenShift

```
rhc app create -a omeka -t php-5.4
```

* Add mysql support to your application

```
rhc cartridge add -a omeka -c mysql-5.1
```

* Add this upstream Omeka quickstart repository

```
cd omeka
git remote add upstream -m master git://github.com/waynegraham/omeka-quickstart.git
git pull -s recursive -X theirs upstream master
```
* Push the quickstart code to your Openshift application

```
git push
```

* Visit appName-yourNamespace.rhcloud.com/install to setup your site!

## Updating

*  On your command-line interface, move to your omeka directory.

```
cd omeka
```

* Pull the upstream changes

```
git pull upstream master
```

* Ensure you have the latest Neatline plugins

```
./update.sh
```

* Push to OpenShift

```
git push
```

* Celebrate

![celebrate](http://www.reactiongifs.com/r/rtr.gif "Celebration")

## Adding Themes
You can find additional theme packages at http://omeka.org/add-ons/themes/
click on the theme image to make sure it will work with this version of Omeka.

[rhc]: https://developers.openshift.com/en/getting-started-client-tools.html
