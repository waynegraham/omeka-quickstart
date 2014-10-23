# Omeka Quickstart on OpenShift Express
Omeka is a free, flexible, and open source web-publishing platform for the display of library, museum, archives, and scholarly collections and exhibitions.

## Installation

1. Create an account at http://openshift.redhat.com/

2. Install the [OpenShift Client Tools][rhc]

3. Create a PHP application on OpenShift

```
rhc app create -a omeka -t php-5.4
```

4. Add mysql support to your application

```
rhc cartridge add -a omeka -c mysql-5.1
```

5. Add this upstream Omeka quickstart repository

```
cd omeka
git remote add upstream -m master git://github.com/waynegraham/omeka-quickstart.git
git pull -s recursive -X theirs upstream master
```
6. Push the quickstart code to your Openshift application

```
git push
```

1. Visit appName-yourNamespace.rhcloud.com/install to setup your site!

## Updating

1. On your command-line interface, move to your omeka directory.

```
cd omeka
```

2. Pull the upstream changes

```
git pull upstream master
```

3. Ensure you have the latest Neatline plugins

```
./update.sh
```

4. Push to OpenShift

```
git push
```

5. Celebrate

![celebrate](http://www.reactiongifs.com/r/rtr.gif "Celebration")

## Adding Themes
You can find additional theme packages at http://omeka.org/add-ons/themes/
click on the theme image to make sure it will work with this version of Omeka.

[rhc]: https://developers.openshift.com/en/getting-started-client-tools.html
