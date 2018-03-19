# DAY 0 - How 

## INTRO
First, you need a server. You can't really learn about administering a remote Linux server without having a one of your own - so today we're going to buy one!

Through the magic of Linux and virtualisation, it's now possible to get a small Internet server setup almost instantly - and at very low cost. Technically, what you'll be doing is creating and renting a VPS  ("Virtual Private Server"). In a datacentre somewhere a single physical server running Linux will be split into a dozen or more Virtual servers using the KVM (Kernel-based Virtual Machine) feature that's been part of Linux since early 2007. There are many hundreds of hosting companies offering low cost VPS deals - and sites like http://lowendbox.com/ that compare them.

As well as a hosting provider, we also need to choose which "flavour" of Linux to install on our server. If you're new to Linux then the range of "distributions" available can be confusing - but the latest LTS ("Long Term Support") version of Ubuntu Server is a popular choice. 
 
These instruction will walk you through using Digital Ocean (http://digitalocean.com) as your VPS hosting provider. They are a latecomer to the business, but are rated highly, with a very simple and slick interface - and low cost of $5 (USD) per month for the minimal server that you'll be creating. (Of course, if you have a strong reason to use another provider, then by all means do so, but be sure to choose Ubuntu Server 12.04 - or later sub-release of it such as 12.04.3)

## Signing up with Digital Ocean
Signup is immediate - just provide your email address and a password of your choosing and you're in!
Follow the "Getting Started" link to provide payment details. Note that if you're not happy giving Digital Ocean your credit card details then choose the "Pay $5 now via PayPal" option - even if you don't have a PayPal account the next screen will allow you to make the payment with a VISA, MaterCard or American Express credit card.

You now have the IP address for your server which you alone are responsible for administering!

