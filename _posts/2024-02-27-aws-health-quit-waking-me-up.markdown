---
layout: post
title: "Aws Health Quit Waking Me Up"
date: 2024-02-27 22:27
comments: true
categories: cloud
exerpt_separator: <!--more-->
---
I work for a big shipping company which uses AWS to host our nextgen platform. We run on a wide variety of AWS resources
and technologies, and thus we depend on AWS being Healthy in our region when our business is running the cash registers.
So, we build alerting out, paging our On-Call Guy whenever [AWS Health][aws-health] tells us something is broken. The trouble
is, our alerting system catches anything and everything, up to and including notifications that a database will be upgraded
to the latest Aurora release two months from now. Woprse, those notifications come outr at very odd times, and our On-Call
Guy (who is often me), complains that he's paged at 3:00am for such nonsense.
<!--more-->

We rotate a one-week On-Call shift. The first few days, as the On-Call Guy, you're either dumbstruck by how many nuisance
pages you get _all night long_ or you don't get bothered and sleep like a baby. It often takes several days before you're
ready to be pissed off by the _all night long_ nuisance pages, but by then, you're so busy heads down working day-to-day
changes thta you don't prioritize fixing the _all night long_ nuisance pages. So, the system has stayed broke for **years**.

I keep threatening to fix it, but I never do. But I recently found this blog post [here][blog-post], that maybe outlines 
how to make a reasonable AWS Health Alerting System, so I'm going to spend some time now figuring this out.

### Design Ideas
I envision a Lambda which reads a json object from an S3 bucket or a record from Dynamodb which contains configuration
data, specifically, perhaps lists of alerts to ignore, convert to daily emails, alert on immediately etc. The Lambda 
would be inbvoked by AWS Health and would itself send the message onto SNS etc. to deliver to the On-Call Guy. Thus
we filter the messages AWS Health gives us into 4 quadrants.

[aws-health]: https://docs.aws.amazon.com/health/latest/ug/aws-health-concepts-and-terms.html#aws-health-events
[blog-post]: https://aws.amazon.com/blogs/mt/using-tag-based-filtering-to-manage-health-monitoring-and-alerting-at-scale/


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
