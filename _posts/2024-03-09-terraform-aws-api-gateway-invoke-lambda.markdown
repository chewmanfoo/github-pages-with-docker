---
layout: post
title: "Terraform AWS API Gateway Invoke Lambda"
date: 2024-03-09 18:02
comments: true
categories: AWS coding Terraform
exerpt_separator: <!--more-->
---
I need to master AWS API Gateway, how it functions, how it manages permissions and how it invokes other resources
like AWS Lambda.
<!--more-->

I'd love to be able to use Lambda to perform AWS API functions, like scaling ASG's or granting and revoking permissions to resources. A knock-knock model for access to an EC2, which adds and then removes X hours later a CIDR to a security group, 
so that you can gain access to the resource for a short time.

See: [Tutorial][terraform-tutorial]

>**Crucial** Before we make this thing permanent, be sure to include an authorizer, otherwise the API Gateway endpoint is security-through-obscurity only.

[terraform-tutorial]: https://registry.terraform.io/providers/hashicorp/aws/2.33.0/docs/guides/serverless-with-aws-lambda-and-api-gateway

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
