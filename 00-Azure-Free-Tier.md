# Day 0 - Creating Your Own Server - with Azure Free Credits

## INTRO

First, you need a server. You can't really learn about administering a remote Linux server without having a one of your own - so today we're going get one - completely free!

Through the magic of Linux and virtualisation, it's now possible to get a small Internet server setup almost instantly - and at very low cost. Technically, what you'll be doing is creating and renting a VPS  ("Virtual Private Server"). In a datacentre somewhere a single physical server running Linux will be split into a dozen or more Virtual servers using the KVM (Kernel-based Virtual Machine) feature that's been part of Linux since early 2007.

As well as a hosting provider, we also need to choose which "flavour" of Linux to install on our server. If you're new to Linux then the range of "distributions" available can be confusing - but the latest LTS ("Long Term Support") version of Ubuntu Server is a popular choice, and what you'll need for this course.

These instructions will walk you through using Azure's free credits.

## Signing up with Azure

Sign-up is fairly simple - just provide your email address and a password of your choosing - along with a phone number for a 2FA - a second method of authentication. Azure can be a bit funny about 'corporate' email addresses, eg using a work address or your own domain. Create a new @outlook or @gmail.com account if so using the link on the sign-up page.
You will need to also provide your VISA or other credit card information.

- Click 'start building in azure'
- Click 'Deploy a virtual machine'
- Click 'Create a linux virtual machine'
- Search and select Ubuntu Server 20.04 LTS
- Use the Standard _D2s_v3 size - this should be comfortably covered by your trial credits for the duration of the course
- Ensure 'SSH Public Key' for authentication and 'generate new key pair' for SSH Public Key source are selected
- Leave 'allow selected ports' as 'ssh (22)' for now
- Click 'Review + Create'
- Azure will generate and download the private key file to SSH onto the box -
- (Windows) double-click this to open on Windows and it will be added to your cert store on the machine
- (Mac OS X and Linux) run the command 'sudo ssh-add -K /link-to-downloaded-file'
- Connect to the machine using `ssh azureuser@PUBLICIP`

Now to fully expose the machine and all ports to the internet:

- Navigate to <https://portal.azure.com/#home>
- Select 'Virtual Machines'
- Select your created virtual machine and select 'Networking' from the settings pane
- Click 'Inbound Port Rules' and 'Add inbound port rule'
- Set 'source port ranges' and 'destination port ranges' to '*' and set 'Source' and 'Destination' to 'any'. Ensure protocol is set to 'any' and action is set to 'allow'. Set the priority to '100' and create an appropriate name
- Click 'Outbound port rules' and 'add outbound port rule'
- Set 'source port ranges' and 'destination port ranges' to '*' and set 'Source' and 'Destination' to 'any'. Ensure protocol is set to 'any' and action is set to 'allow'. Set the priority to '101' and create an appropriate name

This opens all ports and protocols to access from anywhere. While this might be unwise for a production server, it is what we want for this course.

## Remote access via SSH

Ensure your machine is 'running' (if not, click 'start') and connect using the 'connect -> ssh' dropdown and following instructions

You will be logging in as the user *azureuser*. It has been added to the 'adm' and 'sudo' groups, which on an Ubuntu system gives it access to read various logs - and to "become root" as required via the _sudo_ command.

## You are now a sysadmin

Confirm that you can do administrative tasks by typing:

`sudo apt update`

(Normally you'd expect this would prompt you to confirm your password, but because you're using public key authentication the system hasn't prompted you to set up a password - and Azure have configured *sudo* to not request one for "azureuser").

Then:

`sudo apt upgrade`

Don't worry too much about the output and messages from these commands, but it should be clear whether they succeeded or not. (Reply to any prompts by taking the default option). These commands are how you force the installation of updates on an Ubuntu Linux system, and only an administrator can do them.

To logout, type _logout_ or _exit_.

Your server is now all set up and ready for the course!

Note that:

* This server is now running, and completely exposed to the whole of the Internet
* You alone are responsible for managing it
* You have just installed the latest updates, so it should be secure for now
