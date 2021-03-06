# Brthrs Vagrant Box

A Vagrant Box. In the flavours EMP or Wordpress. Created to get your HTML/PHP website or Wordpress website up and running in no time.

What you'll get:

* Ubuntu 16.04 LTS
* nginx 1.10.0
* MySQL 5.7
* PHP 7

With the additional packages:
* Git
* Adminer
* Certbot
* Composer
* Landscape
* Node and npm
* Postfix
* Postgres
* Vim
* WP-CLI
* Bower
* Gulp
* Wordpress 4.7.3 (Wordpress box)

## How To

## Prerequisites
You'll need the following applications on your machine:

- Vagrant (https://www.vagrantup.com)
- VirtualBox (https://www.virtualbox.org)

### Getting Started
Place the `Vagrantfile` of either the `default` or `wordpress` directory in the root of your project. The default one is great for simple HTML and PHP, the latter for Wordpress.

Open Terminal.app, and change to the directory where your code resides and where you placed the `Vagrantfile`, i.e:
```bash
cd ~/Development/willemdafoe-theme
```

Start the virtual machine:
```bash
vagrant up
```

Depending on your host machine and internet connection this can take some time.

While Vagrant is getting your machine up and running you will be asked which network adapter should be used. For example, if you're on Wi-Fi this is probably option '1'.

Your machine is now running!

### Access to your box
Get access to the machine by using:
```bash
vagrant ssh
```

After you ssh in to the machine it will share bits of information with you. One bit is the IP address on which your machine is accessible. It's the second one (often `eth1`).

Even though this address will get you to the running machine it's recommended to add it to your host file for easy access. This is actually required for the Wordpress box since Wordpress is set to run on a specific domain (wordpress.dev).

Add these records to your local machine's hosts file by editing `/private/etc/hosts` in a separate shell:
```bash
sudo vim /private/etc/hosts
```
```
10.0.1.41    vagrant.dev
10.0.1.42    wordpress.dev
10.0.1.43    anythingyouwant.really
```

You can now access your machine on either of the following domains http://vagrant.dev or http://wordpress.dev.

### Working with

#### Wordpress
Make sure your theme files are in your project directory. The vanilla Wordpress theme is still the default one, so make sure to activate yours.

* URL: http://wordpress.dev
* User: `wp`
* Password: `wp`
* Email: `wp@wordpress.dev`

#### MySQL
* Username: `root`
* Password: `root`

#### Adminer
You can access Adminer by visiting http://wordpress.dev/adminer.

## More Info
There is a whole lot more to Vagrant. It's recommended to get yourself familiar with it. Detailed information about 'networking', 'synced folders', 'sftp access', 'removing boxes' is available in the documentation https://docs.vagrantup.com/v2/.
