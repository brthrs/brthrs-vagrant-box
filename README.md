# Brthrs Vagrant Box

A Vagrant Box. Two flavours. Created to get your site or Wordpress theme up and running quick.

What you'll get:

* Ubunutu Precise 64 (hashicorp/precise64)
* Apache
* PHP
* MySQL
* Vim
* Wordpress

## How To

### Getting Started
You'll need the following applications on your machine:

- Vagrant (https://www.vagrantup.com)
- VirtualBox (https://www.virtualbox.org)

Place either the `default` or `wordpress` `Vagrantfile` next to your code. The first one is great for simple html and php sites, the latter for Wordpress.

Open `Terminal.app`, and change to the directory where your code resides and where you placed the `Vagrantfile`.

For example:

```cd ~/Development/willemdafoe-theme```

Start the virtual machine.

```vagrant up```

Depending on your host machine and internet connection this can take some time.

While Vagrant is getting your machine up and running you will be asked which network adapter should be used. For example, if you're on Wi-Fi this is probaly option '1'.

Your machine is now running!

### Access to your box
Get access to the machine by using:

```vagrant ssh```

After you ssh in to the machine it will share bits of information with you. One bit is the IP address on which your machine is accessible. It's the second one (`eth1`).

Eventhough this address will get you to the running machine it's recommended to add it to your host file for easy access. This is actually required for the Wordpress box since Wordpress is set to run on a specific domain (wordpress.dev).

Add these records to your local machine's hosts file. You can do this by running `sudo vim /private/etc/hosts` in a separate shell.

For example:

* ```192.168.1.43		brthrs.dev```
* ```192.168.1.44		wordpress.dev```

You can now access your machine on either of the following domains:

* http://brthrs.dev
* http://wordpress.dev

### Working With

**Wordpress**

Make sure your theme files are in your project directory. The vanilla Wordpress theme is still the default one, so make sure to activate yours.

* URL: http://wordpress.dev/wp-admin
* Username: `wp`
* Password: `wp`

**MySQL**

* Username: `root`
* Password: `root`

**SFTP to Vagrant**
1. Look for your KEY by using following command: vagrant ssh-config
2. Copy the KEY and past it in the "Go to folder" in finder
3. add it the KEY the Transmit
4. Servers = IP
5. Username = "vagrant" & password = BLANK

Tutorial video: http://d.pr/v/12wD6

## More Info
There is a whole lot more to Vagrant. It's recommended to get yourself familar with it. Detailed information about 'networking', 'synced folders', 'sftp access', 'removing boxes' is available in the documentation https://docs.vagrantup.com/v2/.
