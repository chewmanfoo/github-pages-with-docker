---
layout: post
title: "Conflicting Scopes And How To Make Them Play Nice"
date: 2012-04-04
comments: true
categories: 
exerpt_separator: <!--more-->
---

If you do enough with Rails 2, you'll be using named scopes (I think they're frowned upon in Rails 3).  I use named scopes for everything, particularly when I need to write complex queries which involve joins of tables.  In this example, I have these models: an Rca, a Root Cause Analysis document, which is a report on a system failure and why it happened, a GenericProfile, which is a generalization of a System which might have a failure, an ImplementationType, which is a way a System might be implemented, a SoftwareRelease, which is the software the GenericProfile (System) might be running, and a FeatureGroup, which is a collection of SoftwareReleases.  When talking about Rcas, we need to group them by ImplementationType and by FeatureGroup, so we can say 'show me all the Rcas that refer to this System type', or 'show me all the Rcas that refer to this method of implementation'.  We can do this with named scopes.
<!-- more -->

Here's how I implemented the named scopes `by_feature_group` and `by_implementation_type`:

Liquid error: undefined method `Py_IsInitialized' for RubyPython::Python:Module

Liquid error: undefined method `Py_IsInitialized' for RubyPython::Python:Module

This all works fine if they're used separately:

Liquid error: undefined method `Py_IsInitialized' for RubyPython::Python:Module

But, if they're chained (as normal AR scopes can be easily), problems can occur:

Liquid error: undefined method `Py_IsInitialized' for RubyPython::Python:Module

Why is this happening?

It's happening because the magic of AR is merging the two complex queries together (for efficiency, and because it wouldn't work if it didn't), and the two queries aren't merging well.  Specifically, `by_feature_group` joins on generic_profiles, but so does `by_implementation_type`, so the query mentions generic_profiles more than once, and mysql can't tell which generic_profiles you're talking about.  If only mysql were smarter!  To solve this problem, we could do one of two things (the second is better):


remove the separate scopes and write a single new scope `by_feature_group_by_implementation_type`
alias generic_profiles in one of the scopes (let your hamster pick which one)



The second option is better because it still allows the separate scopes to remain separate. The new `by_implementation_type` scope now looks like this:

Liquid error: undefined method `Py_IsInitialized' for RubyPython::Python:Module

Cool, eh?

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
