---
layout: post
title: "Erlang On Aws"
date: 2012-03-18 22:48
comments: true
categories: 
exerpt_separator: <!--more-->
---
AWS and Amazon Elastic Cloud could be the best playground for erlang projects.  I'm going to experiment with using EC2 to build a variety of erlang 'Hello World' projects.

<!-- more -->

## Goals

### Virtual Machines

Figure out how to build AWS Amazon Linux (free tier) images the same way vagrant does images with Virtualbox.

### Networking

Figure out how to get various EC2 images to talk to each other securely (using AWS VPC).

Here's some links:
    * [Erlang for AWS][erlang-for-aws]
    * [mochiweb][mochiweb]
    * [Heroku Erlang][heroku-buildpack-erlang]
    * [AWS Microinstances with Erlang][aws-micro-erlang]
    * [Erlang Comet Chatserver][erlang-chat-server-comet]
    * [Erlang Socket IO][socket.io-erlang]
    * [Vagrant AWS Gem][vagrant-aws-gem]

[erlang-for-aws]: https://github.com/x6j8x/erlaws/tree
[mochiweb]: https://github.com/mochi/mochiweb
[heroku-buildpack-erlang]: https://github.com/archaelus/heroku-buildpack-erlang
[aws-micro-erlang]: http://j2labs.tumblr.com/post/4679269154/instantiating-aws-micro-instances-with-erlang
[erlang-chat-server-comet]: http://chrismoos.com/2009/09/28/building-an-erlang-chat-server-with-comet-part-1/
[socket.io-erlang]: https://github.com/yrashk/socket.io-erlang
[vagrant-aws-gem]: https://github.com/mlinderm/vagrant-aws

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
