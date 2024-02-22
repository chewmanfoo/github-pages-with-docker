---
layout: post
title: "Generic Multiple Attachments In Rails"
date: 2012-03-23
comments: true
categories: 
exerpt_separator: <!--more-->
---
If you use paperclip for attaching pictures to models in Rails, you've probably run into this problem.  At first, you've added a picture called 'diagram' to an MVC called WhitePaper, and it works fine.  You can click on a link (diagram_url) and it pops the picture up in your browser, and everybody says Wow!  Then people start asking you to attach other pictures to other models, and more pictures to the WhitePaper model, and you discover that you've become an idiot.  Every time somebody asks for an attachment, you have to add code.  And you thought Rails was agile!
<!-- more -->

What you really need is a truly generic AttachedDocument which can be added to any model with a line `has many attached_documents` or `attachable`.  You ought to be able to render a view of 1 - n AttachedDocuments, add other attachments and remove existing ones.  Later on, you might want to keep versions of AttachedDocuments, so you can revert a change if necessary. And somehow, the new magic AttachedDocument ought to be able o sense it's document's mime type, size etc., and create resuzes and thumbnails using ImageMagik with ease.  Surely it's possible.  Or has it already been done?  by this I mean, has anyone already rolled Paperclip into a generic AttachedDocuments gem?

## CarrierWave attachments

I'm watchng ryanb's excellent tutorial on using CarrierWave for file atachments as an alternative to Paperclip.  See here: [Railscast][railscast-link].  In this project, he creates a Gallery model and is able to create multiple Galleries and add multiple picture attachments to each Gallery.  This might be close to what I need - if I convert his Gallery model to a GenericAttachments model, then figure out how to allow multiple GenericAttachment's per model-with-generic-attachments, then figure out how to allow a fixed set of 'safe' mimetypes like png, jpeg, pdf, doc and xls, this might just work.

## Links

   * [paperclip][paperclip]
   * [discussion on googlecode][googlecode-discussion]
   * [paperclip-related gems][poaperclip-related]

[railscast-link]: http://railscasts.com/episodes/253-carrierwave-file-uploads
[paperclip]: https://github.com/thoughtbot/paperclip
[googlecode-discussion]: http://groups.google.com/group/paperclip-plugin/browse_thread/thread/d03cac32d2abd4ab
[paperclip-related]: http://rubygems.org/search?utf8=%E2%9C%93&amp;query=paperclip

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
