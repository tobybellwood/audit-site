# govCMS Site Audit

This project is to help site building using the govCMS distribtion audit their site builds against acceptable use for hosting on the [govCMS SaaS platform](https://www.govcms.gov.au/how-it-works/compare-saas-and-paas).

This tool is used as a gateway for onboarding and launching sites on the platform. If you are a site builder, we recommend you use the tool prior to a onboard/forklift request to ensure your site meets the acceptable practices for hosting on the SaaS platform


## Installation

To use the tool, you'll need to install it. This tool is built on [Composer](https://getcomposer.org). You'll need to first install that. Please see the [installation instuctions](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

Once you have composer installed, clone this git repository and install the dependancies with composer:

```
git clone git@github.com:govCMS/audit-site.git
cd audit-site
composer install
```

If you wish to run browser based checks (e.g. page weight check), then you will require Phantomas to be installed on your local system. Note that these checks are optional.

First install Node:

```
brew install node
```

And then use NPM to install phantomas:

```
npm install --global --no-optional phantomas phantomjs-prebuilt@^2.1.5
```


## Usage

To run the audit you'll need to have your site referenceable via a [Drush alias](https://github.com/drush-ops/drush/blob/master/examples/example.aliases.drushrc.php). The Site Audit tool relies on the connection details to the site be setup as a drush alias already.

Before you conduct an audit you should always ensure your tool is up to date.

```
git pull origin master
composer update
```

Conducting the audit is as simple as running this one command with the correct drush alias.

```
./audit-site.sh @site.env
```

The audit will inform you through commandline output on the results of the audit. At the end of the audit, it will also provide an HTML report that you can open in a browser.
