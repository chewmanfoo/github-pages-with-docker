---
layout: post
title: "Throw Everything On Aws"
date: 2013-04-14 04:12
comments: true
categories: 
exerpt_separator: <!--more-->
---
I am paying $40 a month to linode for a 1Gb slice with no practical limits on transfers (there may in fact be limits, but I haven't experienced them.)  I'm exploring whether I can move the services I run on linode to AWS, free tier, so save some $$.

## iRedMail

I run a wiki and a mail server.

I found this: [How to Install Redmail on EC2][redmail]

The free tier allows Amazon linux as well as ubuntu.  The transfer limits may be an issue with a mail server.  I'm debating on imap mail servers available online. The upshot is that when I get turned into a forward for spam, I have to fight it on my linode server, but the imap provider would be responsible for it (time = money, so it's often a good deal).

## Amazon Glacier

Backups are essential.  You don't value them until you need them, but when you need them, and you don't have them, it could be devastating.  You need a system which will backup your critical files periodically, and perform the function whether you like it or not.  Set it and forget it.  And it always helps if somebody else is contractually obligated to manage the media, store the tapes offsite, restore upon demand.

Then somebody brings up the issue of cost.  There are several different options for online backup solutions out there, and they vary widely on cost.  Amazon Glacier's model is designed to get you up and running quickly with little upfront cost and a tiny monthly maintenance fee.  It only costs you if/when you need to restore your stuff.  Costwise it's smart.  I recommend it.

In order to bring easy periodic backups to your linux instance using Amazon Glacier, I recommend this lovely gem: [link][glacier] This works also, but it's more of a pain in the ass: [link][epsilontik]

[redmail]: http://www.inboxs.com/index.php/linux-os/ec2-aws/10-how-to-install-iredmail-on-ec2
[glacier]: https://github.com/uskudnik/amazon-glacier-cmd-interface
[epsilointik]: http://blog.epsilontik.de/?page_id=68

<!-- see https://github.com/Shopify/liquid/wiki/Liquid-for-Designers for stuff 
# H1
## H2
[I'm an inline-style link](https://www.google.com)
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png 'Logo Title Text 1')
```javascript
var s = 'JavaScript syntax highlighting';
alert(s);
```
   * an unordered list item (note a newline is required before the list begins)
   1. an ordered list item
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
-->
