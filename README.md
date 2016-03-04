# Magento 2 standard installation using composer

---

***Official installation note**: Since Magento released officialy version 2.0.0, they added the `composer project-create` command in the documentation. You can find more information here: <http://devdocs.magento.com/guides/v2.0/install-gde/prereq/integrator_install.html#integrator-first-composer-ce>*

---

![Version of Magento](https://img.shields.io/badge/Version%20of%20Magento%20installed%20by%20this%20project-2.0.2-green.svg)

As you probably know, Composer is used in Magento 2.  
One of the fine part is that Magento 2 can be totally (ok, almost) included in the `vendor` directory.

## Use it (aka Install Magento 2 using composer)

It is really easy to use. **But please read the Requirements** part below before trying to install Magento 2 as a composer dependency.

The `create-project` command accepts multiple arguments like:

* `-s dev`: set the stability to `dev`
* `--ignore-platform-reqs`: ignore the platform requirements (version of PHP…)
* `--prefer-source`: use git clone instead of using the cache if you have one for the dependencies

According to this if we are on the machine where you want to run Magento 2, you just have to run:

	composer create-project magento-hackathon/magento2-standard destination

Replace the `destination` with the name of the directory where you want to put Magento 2.

If you are, like me, on your own machine and you don't have all the dependencies for Magento (because you use virtual machines):

	composer create-project --ignore-platform-reqs magento-hackathon/magento2-standard destination

## Demos

[![Video on Toutube](https://i.ytimg.com/vi/gmz9h8g6Gk8/maxresdefault.jpg)](https://www.youtube.com/watch?v=gmz9h8g6Gk8)

[![Example with asciicast](https://asciinema.org/a/30082.png)](https://asciinema.org/a/30082)

## What does it do?

It's really simple in fact. We just say to composer that Magento 2 is a dependency and we update the autoload to make the setup wizard work.

No big deal. Just the time to find out how it works.

## Requirements

This repository isn't on packagist yet. And because of that you can't run the `create-project` command of composer with this beautiful code.

You have to add this repository into your composer global configuration.

Please run this command in your console: (or your VM, or your server…):

	composer config -g repositories.magento2-standard vcs https://github.com/magento-hackathon/magento2-standard
	
## Questions & Answers

* **I use a VM and I want to clone Magento 2 directly in my computer but some requirements are missing. How can I do?**

	If like me you want to use the performance of the IO of your own machine and probably use your personnal token on github you can ask to composer to not check on the platform requirements:

	You just have to use the command line option `--ignore-platform-reqs` in your composer command.  

	See the [create-project command][create-project-command].

## How to contribute

Feel free to send pull requests.

If you want to use your own repository and use the last commit for your tests, you have to use the `-s dev` argument in your composer command, like:

	composer create-project -s dev magento-hackathon/magento2-standard destination

## Contributors

* Jacques Bodin-Hullin ([@jacquesbh](https://github.com/jacquesbh) / [jacquesbh](http://twitter.com/jacquesbh)), Author & Maintainer


[create-project-command]: https://getcomposer.org/doc/03-cli.md#create-project
