---
layout: page
weight: 0
title: Email Reports
navigation:
  show: true
---

The Email Reports tab of the website allows you to view logs of all your bounced emails, as well as your unsubscribed customers. In addition to viewing these logs on the web, you can save these lists as either .csv or .txt files, or print the list. These logs are divided into the following categories.


With the exception of the Block list, all emails listed on these lists will be dropped from any future attempts for delivery, this is because redelivering emails to these addresses will most likely be unsuccessful, and definitely negatively impact your Sender Reputation.

You can also control the way bounces are dealt with for your account via a settings button available from the [Bounce List page](http://sendgrid.com/bounces).

![]({{root_url}}/images/email_reports.png)

These settings allow you to purge either hard or soft bounces after a certain number of days. Additionally, you may specify whether or not you would like bounce messages from recipient servers to be forwarded via email, and if so, you may specify an address which these messages to be forwarded to. (As opposed to the from address on the bounced email.)
