# Day 0 - Creating Your Own Server - with AWS Free Tier

## INTRO

First, you need a server. You can't really learn about administering a remote Linux server without having one of your own - so today we're going get one - completely free!

Through the magic of Linux and virtualization, it's now possible to get a small Internet server setup almost instantly - and at very low cost. Technically, what you'll be doing is creating and renting a VPS ("Virtual Private Server"). In a datacentre somewhere, a single physical server running Linux will be split into a dozen or more Virtual servers, using the KVM (Kernel-based Virtual Machine) feature that's been part of Linux since early 2007.

In addition to a hosting provider, we also need to choose which "flavour" of Linux to install on our server. If you're new to Linux then the range of "distributions" available can be confusing - but the latest LTS ("Long Term Support") version of Ubuntu Server is a popular choice, and what you'll need for this course.

These instructions will walk you through using Amazon's AWS "Free Tier" (<http://aws.amazon.com>) as your VPS hosting provider. They are rated highly, with a very simple and slick interface. Although we'll be using the Free Tier, be warned that you will need to provide valid credit card information. (Of course, if you have a strong reason to use another provider, then by all means do so, but be sure to choose Ubuntu Server 20.04)

## Signing up with AWS

Sign-up is fairly simple - just provide your email address and a password of your choosing - along with a phone number for a 2FA - a second method of authentication.
You will need to also provide your VISA or other credit card information.

* For Support Plan, choose "Basic Plan/Free"

Logout, then login again, and then select:

* Services - from the top menu
* EC2 - from the list of services

In "AWS speak" the server we'll create will be an "EC2 compute instance" - so now choose "Launch Instance". You will be presented with several image options - choose one with "Ubuntu Server 20.04 LTS" in the name.
At the next screen you'll have options for the type - typically only "t2.micro" is eligible for the Free Tier, but this is fine, so select to "review and Launch"
At the review screen there will be an option "Security Groups" - this is in fact a firewall configuration which AWS provides by default. While a good thing in general, for our purposes we want our server completely exposed, so we'll edit this to effectively disable it, like this:

* Select "Configure Security Group"
* Select "Add Rule"
* Type: "All traffic", Source: "Anywhere"

This opens all ports and protocols to access from anywhere. While this might be unwise for a production server, it is what we want for this course.

Now select "Launch". When prompted for a key pair, create one.

Your server instance should now launch, and you can login to it by:

* Services, EC2, Running instances, Connect

## Remote access via SSH

You should see an "IPv4" entry for your server, this is its unique Internet IP address, and is how you'll connect to it via SSH (the Secure Shell protocol) - something we'll be covering in the first lesson.

This video, "How to Set Up AWS EC2 and Connect to Linux Instance with PuTTY" (<https://www.youtube.com/watch?v=kARWT4ETcCs>), gives a good overview of the process.

You will be logging in as the user *ubuntu*. It has been added to the 'adm' and 'sudo' groups, which on an Ubuntu system gives it access to read various logs - and to "become root" as required via the _sudo_ command.

## You are now a sysadmin

Confirm that you can do administrative tasks by typing:

`sudo apt update`

(Normally you'd expect this would prompt you to confirm your password, but because you're using public key authentication the system hasn't prompted you to set up a password - and AWS have configured *sudo* to not request one for "ubuntu").

Then:

`sudo apt upgrade`

Don't worry too much about the output and messages from these commands, but it should be clear whether they succeeded or not. (Reply to any prompts by taking the default option). These commands are how you force the installation of updates on an Ubuntu Linux system, and only an administrator can do them.

To logout, type _logout_ or _exit_.

Your server is now all set up and ready for the course!

Note that:

* This server is now running, and completely exposed to the whole of the Internet
* You alone are responsible for managing it
* You have just installed the latest updates, so it should be secure for now
