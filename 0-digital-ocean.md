# DAY  - Creating Your Own Server - with Digital Ocean

## INTRO
First, you need a server. You can't really learn about administering a remote Linux server without having a one of your own - so today we're going to buy one!

Through the magic of Linux and virtualisation, it's now possible to get a small Internet server setup almost instantly - and at very low cost. Technically, what you'll be doing is creating and renting a VPS  ("Virtual Private Server"). In a datacentre somewhere a single physical server running Linux will be split into a dozen or more Virtual servers using the KVM (Kernel-based Virtual Machine) feature that's been part of Linux since early 2007. There are many hundreds of hosting companies offering low cost VPS deals - and sites like http://lowendbox.com/ that compare them.

As well as a hosting provider, we also need to choose which "flavour" of Linux to install on our server. If you're new to Linux then the range of "distributions" available can be confusing - but the latest LTS ("Long Term Support") version of Ubuntu Server is a popular choice, and what you'll need for this course. 
 
These instruction will walk you through using Digital Ocean (http://digitalocean.com) as your VPS hosting provider. They are rated highly, with a very simple and slick interface - and low cost of $5 (USD) per month for the minimal server that you'll be creating. (Of course, if you have a strong reason to use another provider, then by all means do so, but be sure to choose Ubuntu Server 18.04)

## Signing up with Digital Ocean
Signup is immediate - just provide your email address and a password of your choosing and you're in!

* Choose "Manage, Droplets" from the left hand sidebar. (a "droplet" is Digital Ocean's cute name for a server!)
* Select the image "Ubuntu 18.04"
* For plan, choose "Starter"
* You'll be prompted to start a $40/m plan, but select "Shoe all plans', and select the $50/mo one - that's fine for this course.
* You don't need to add any block storage
* Select whichever region you wish. 
* Authentication - choose "One time password"
* Choose a hostname, the default ones are pretty ugly

## Tweaking your new server
You should have received a password for the "root" user in your email. Select your droplet and "Access" from the left hand sidebar and you should be able to login to the conole using this. Use the login name "root", and note that the password won't show as you type or paste it.

You'll be prompted to change your password. Select a long and secure one - this is important, because your server is on the open Internet and will be under immediate and sustained attack from bots attempting to "brute force" the root password.

For the course we use the Best Practice of not logging as "root" remotely, so we'll create an ordinary user account, but give it the power to "become root" as necessary, like this:

    sudo adduser snori74
    sudo usermod -a -G adm snori74
    sudo usermod -a -G sudo snori74

Obviosly replace 'snori74' with your name - and this will be the account that you use to login and work with your server. It has ben added to the 'adm' and 'suo' groups, which on an Uuntu system gives it access to read variuos logs and to "beome root" as required vi the _sudo_ command.



You now have the IP address for your server which you alone are responsible for administering!

     
