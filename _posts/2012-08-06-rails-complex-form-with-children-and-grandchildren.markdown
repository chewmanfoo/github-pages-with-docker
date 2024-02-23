---
layout: post
title: "Rails Complex Form With Children And Grandchildren"
date: 2012-08-06 03:36
comments: true
categories: 
exerpt_separator: <!--more-->
---
I love Rails forms and the simplicity of AR associations in forms.  Ryab Bates explains in this railscast how easy it is to include child classes in associations in a form, and have all creates and updates happen automatically: [Railscast][railscast]].  What Ryan doesn't cover, is the possibility that the model's child may have children (grandchildren).
<!-- more -->

After fighting with this for a week or so, I figured it out.  It's all in the controller, where the child and grandchild is created at first:

Liquid error: undefined method `Py_IsInitialized` for RubyPython::Python:Module

And in the helper method, where code is given to the javascript to add the new fields when Add * is clicked:

Liquid error: undefined method `Py_IsInitialized` for RubyPython::Python:Module

Note that I had to change Ryan's helper adding in the second association and a bit of code to realize the grandchildren objects. Not only do you have to create the grandchild, but you have to associate the grandchild with the child so the form works properly.

There's probably a better solution.

[railscast]: http://railscasts.com/episodes/196-nested-model-form-revised

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
