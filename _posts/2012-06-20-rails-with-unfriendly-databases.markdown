---
layout: post
title: "Rails With Unfriendly Databases"
date: 2012-06-20 03:29
comments: true
categories: 
exerpt_separator: <!--more-->
---
We all know that Rails is _Opinionated_ when it comes to the backend database schema.  Tables are named after the plural word describing what they contain (`posts`, not `Post` or `post` or `boatload_o_posts`).  Tables have a primary key called `id`.  In fact, the easiest way to get along with rails from the gitgo is to let rails build it's backend database for you, using migrations.  That's crucial to getting your Rails mojo kung-fu working.  But what hapens when you need to connect your Rails app to an unfriendly database?  What if you have to read data from a database designed by some one who, gasp!, doesn`t do Rails?  What then???

I recently added a report to my corporate site survey Rails project which needed to pull data from a bunch of joined tables in a database which was the backend for Manage Engine's [Supportcenter][supportcenter].  I really don't like supportcenter, and I _really_ don't like supportcenter's database.  Wow what a flaming sack of dogshit that thing is.
<!-- more -->

## Connecting to the unfriendly database

You can either add login/password to your model, or add them to database.yml.  I chose to add them to database.yml:

Liquid error: undefined method `Py_IsInitialized` for RubyPython::Python:Module

Then, we`ll use these credentials to connect to the database and run queries in our model.

## A new Rails model for the unfriendly database`s table

Create a new model which inherits from ActiveRecord, like so:

Liquid error: undefined method `Py_IsInitialized` for RubyPython::Python:Module

## Queries and results

Now we can add queries to the Workorder model which pull from this unfriendly supportcenter database:

Liquid error: undefined method `Py_IsInitialized` for RubyPython::Python:Module

Note the godawful table attributes in the supportcenter database.  If you`re sitting on your couch late at night, and you hear a knock on the door, and you go to the door and open it and look around, and if you see the supportcenter database on your doorstep, do not stomp out the fire!!!

Therefore, we can slice and dice the result array from this query within the controller:

Liquid error: undefined method `Py_IsInitialized` for RubyPython::Python:Module

It works like a charm.

[supportcenter]: http://www.manageengine.com/products/support-center/

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
