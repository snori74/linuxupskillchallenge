# DAY  - Creating Yoer Own Server - with Digital Ocean

## INTRO
First, you need a server. You can't really learn about administering a remote Linux server without having a tame one of your own - so today we're going to buy one.

Through the magic of Linux and virtualisation, it's now possible to get a small Internet server setup alomost instantly - and at very low cost. Technically, what you'll be doing is creating and renting a VPS  ("Virtual Private Server"). In a datacentre somewhere a single physical server running Linux will be split into a dozen or more Virtual server using the KVM (Kernel-based Virtual Machine) feature that's been part of Linux since early 2007. There are many hundreds of hosting companied offering lowcost VPS deals - and sites like http://lowendbox.com/ that compare them.

As well as a hosting provider, we also need to choose which "flavour" of Linux to install on our server. If you're new to Linux then the range of "distributions" available can be confusing - but the latest LTS ("Long Term Support") version of Ubuntu Server is a reasonable choice. 
 
These instruction will walk you through using Digital Ocean (http://digitalocean.com) as a provider. They are a latecomer to the business, but are rated highly, with a very simple and slick interface and low cost of $5 (USD) per month for the miniaml server that we'll be creating. Of course, if you have a strong reason to use another provider, then by all means do so - but be sure to choose Ubuntu Server 12.04 (or later realease of it such as 12.04.3).

## Signing up with Digital Ocean
Signup is immediated - just provide your email address and a password of your choosing and you're in!
Follow the "Getting Started" link to provide payment details. Note that if you're not happy giving Digital Ocean you're credit card details then choose the "Pay $5 now via PayPal" option - even if you don't have a PayApl account te nextscreen wioll allow you to make the payment with a VISA, MaterCard or American Exprwss credit card.
.


You now have the IP address for your server which you alone are responsible for administering!
Your server will be running either Ubuntu or Debian - while these are two distinct "distributions" of Linux, the commaline administration of them is nearly identical. To become a fully-rounded Linux server admin you should become comfortable working with different versions of Linux, but for now Debian/Ubuntu is a good choice. 

Once you have reached a level of comfort at the command-line then you'll find your skills transfer not only to all the standard Linux variants, but also to Android, Apple's OSX, OpenBSD, Solaris and IBM AIX. Throughout the course you'll be working on Linux - but in fact most of what is covered is applicable to any system in the "UNIX family" - and the major differences between them are with their graphic user interfaces such as Gnome, Unity, KDE etc - none of which you’ll be using!

## YOUR TASKS TODAY:

* Connect and login remotely your server 
* Run a few simple simple commands to check the status of your servers
* Change your password

## INSTRUCTIONS

Remote access used to be done by the simple *telnet* protocol, but now the much more secure SSH (“Secure SHell) protocol is always used.

If you're using any Linux or Unix system, including Apple's OS X, then you can simply open up a "terminal" session and use your command-line *ssh* client like this:

	ssh user@<ip address>	 

For example:

	ssh support@192.123.321.99

On an OSX machine you'll normally access the command line via Terminal.app - it's in the Utilities sub-folder of Applications. On Linux distributions with a menu you'll typically find it under "Applications menu -> Accessories -> Terminal", "Applications menu -> System -> Terminal" or "Menu -> System -> Terminal Program (Konsole)"- or you can simply search for your terminal application.

On Microsoft Windows there is no suitable client built-in, or available from Microsoft - so the "standard" is a free program called PuTTy. It is written and maintained by Simon Tatham, so get it directly from his site at: http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html You can download and install the full suite with "Windows installer" version. If you don't have permission to install software on the computer you are using then you can run PUTTY.exe directly from its download page without installing it. There are other SSH clients, and any should be suitable for the course.

The first time you connect to your server, you’ll receive a warning that you're connecting to a new server - and be asked if you wish to "cache the host key". Do this. Now, if you get a warning in future connections it means that either: (a) you are being fooled into connecting to a different machine or (b) someone may be trying a "man in the middle" attack.

So, now login to your server with the provided login details - and remember that Linux is case-sensitive regarding user names, as well as passwords.

Once logged in, notice that the "command prompt” that you receive ends in  "$" - this is the convention for an ordinary user, whereas the "root" user with full administrative power has a # prompt.

Try these simple commands:

	ls           	 
	uptime   	 
	free       	 
	df -h      	 
	uname -a   

Now use the *passwd* command to change your password. To do this, think of a new, secure password, then simply type *passwd*, press “Enter” and give your current password when prompted, then the new one you've chosen, confirm it  - and then WRITE IT DOWN somewhere.

A common Linux convention is that simply selecting text in the terminal session does a "copy", and within the terminal a RightClick is considered a paste. Test this out by copying some text from Windows or OSX and right-clicking into your terminal session - and also try the reverse: selecting text in the terminal and pasting into windows. Getting the hang of this is a useful skill.

Log out by typing *exit*.

## POSTING YOUR PROGRESS

Regularly posting your progress is an important part of the GREP101 process.

In future days, you'll mark your progress by creating files or folders on your server as directed (and which we'll be monitoring), but for now simply drop a quick note to tutor@grep101.com to let us know that you're underway.

If you wish, post a small introduction of yourself for your "classmates" onto the the web forum. No need to be too specific: something like  "mid 20s Apple guy, not very technical" or "retired old-timer programmer looking to keep the brain active" is fine.

## WRAP

You now have the ability to login remotely to your own server. Perhaps you might now try logging in from home and work - even from your smartphone! As a server admin you'll need to be comfortable logging in from all over. (Note you can run PUTTY.exe directly from its download page without installing it - just google for "putty.exe download" to get to the page. You can also potentially use JavaScript ssh clients (search for consolefish), or from a cybercafe;  but these options involve putting more trust in third-parties than most sysadmins would be comfortable with when accessing production systems.

You'll be spending a lot of time in your SSH client, so it pays to spend some time customising it. At the very least try "black on white" and "green on black" - and experiment with different monospaced fonts, ("Ubuntu Mono" is free to download, and very nice).

## EXTENSION

If this is all too easy, then spend some time reading up on:

* "SSH Tunneling"
* "Password-less SSH login"

## RESOURCES

* ["Using PuTTY for SSH (Windows)"](http://kb.mediatemple.net/questions/1595/Using+SSH+in+PuTTY+%28Windows%29#gs )
* [Comparing CENTOS and Ubuntu for servers](http://serverfault.com/questions/53954/centos-vs-ubuntu)
* [A Beginners Guide to SSH](http://www.gamexe.net/other/beginner-guide-ssh/)


