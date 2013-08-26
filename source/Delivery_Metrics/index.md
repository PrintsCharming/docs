---
layout: page
weight: 100
title: Delivery Metrics Index
navigation:
  show: true
---

SendGrid offers statistics a number of different metrics to report on what is happening with your messages.

![]({{root_url}}/images/delivery_metrics.png)


{% anchor h2 %} Metrics {% endanchor %}
 
{% info %} Most of the metrics we track for you are available from our web interface or through our [Event API]({{root_url}}/API_Reference/Webhooks/event.html). We are working on adding the new beta statistics. {% endinfo %}
 
{% info %} For a detailed list of common error messages, please visit our [Email Error Messages]({{root_url}}/Delivery_Metrics/email_error_messages.html) page. {% endinfo %}
 
{% anchor h3 %} Requests {% endanchor %}


A request is an email sent and is reported in your SendGrid dashboard every time our servers get a request from your application or server to send an email to one of your customers.


{% anchor h3 %} Delivered {% endanchor %}


A delivery is recorded when a request to send an email results in an email being delivered to the end recipient. However, delivered does not necessarily mean that your email is in the recipient's inbox. Delivered means the message was accepted by the receiving server, but they does not necessarily mean the message reached the inbox.


{% info %} If an email is indicated as delivered you can be certain that it was not deferred by the ISP. {% endinfo %}
 
{% anchor h3 %} Clicks & Unique Clicks {% endanchor %}


The “Clicks” percentage is the total number of times your users have clicked on the various links within your emails, divided by the total number of Delivered messages. The “Unique clicks” percentage is the number of unique individuals that have clicked the links in your emails, divided by the total number of Delivered messages. This requires that the Click Tracking app be enabled.


{% anchor h3 %} Opens & Unique Opens {% endanchor %}


SendGrid inserts a small, transparent image into all messages that are being tracked for Opens. When the client application loads images, it pulls the image data from SendGrid servers and registers an Open event. Not all email clients load images by default. Microsoft's Outlook, Apple's Mail.app, Mozilla's Thunderbird, and Google's Gmail do not load images. As such, there may be many occasions where recipients will have received a message, opened it, and even clicked on a link, and it will never be counted as opened. The "Opens" percentage is the total number of times your users opened your emails, divided by the total number of Delivered messages. The “Unique opens” percentage is the number of unique individuals that have opened your emails, divided by the total number of Delivered messages. This requires that the Open Tracking app be enabled.


{% anchor h3 %} Unsubscribes {% endanchor %}


In order to maintain compliance with [CAN-SPAM laws](http://business.ftc.gov/documents/bus61-can-spam-act-compliance-guide-business "CAN-SPAM"), any email that is sent in bulk to a mass audience must include a subscription management link. SendGrid provides a "Subscription Tracking" app that automatically adds this link to your emails. When someone clicks that link within their email, they are added to your "unsubscribe" list. Any recipients that are added to this list will be excluded from future mailings.

It's no surprise that sending messages to addresses that have explicitly unsubscribed from any of your email messages is detrimental to your reputation as a sender. While this functionally only applies to one-to-many message formats (i.e., marketing emails) and not to transactional email messages, make sure to include subscription management functionality in your marketing marketing emails and other mass messaging.

![]({{root_url}}/images/delivery_metrics_apps.png)


{% info %} you can enable Click, Open, and Subscription Tracking in the [Apps](http://sendgrid.com/app/) section of your SendGrid account. {% endinfo %}
 
{% anchor h3 %} Bounces & Repeat Bounces {% endanchor %}


A **bounce** occurs when a sent message is rejected by the receiving mail server. The most common causes for bounced email messages include a misspelled email address, a nonexistent email address, or a full recipient inbox. A **repeat bounce** is when an address has bounced, then bounced a second time and logged to the Bounce List, but you ask us to send to it again. Our system does not attempt to deliver the message, because the system 'knows' that address is bad. This shows up on the Email Activity tab as a **drop** with the reason "bounced address", and as a "repeat bounce" on the Statistics tab.

[View your Bounces](http://sendgrid.com/bounces)


{% anchor h3 %} Hard Bounce {% endanchor %}


This type of **bounce** occurs when the receiving server returns a 500-class error, communicating no additional attempts to deliver to that server or email address are needed. An common reason for a hard bounce is "no mailbox for user."


{% anchor h3 %} Spam reports & repeat spam reports {% endanchor %}


If a recipient of your email feels that they received it in error, or simply did not wish to get the email from you, they may click the "report spam" or "junk" button. **Spam reports** can negatively affect your reputation and deliverability, so it is very important to make sure you send to people who really want your messages. You should always include a clear, easy way to opt out of future messages from your organization, by way of a subscription management link. Finally, a clear and fair initial opt-in process will mitigate potential spam reports down the road. **Repeat Spam reports** are the number of messages that were sent to addresses that had reported mail as spam, and were therefore dropped. Think of the number more as "number of emails suppressed because the address reported email as spam".

[View your Spam Reports](http://sendgrid.com/spamReports "Spam Reports")


{% anchor h3 %} Invalid email {% endanchor %}


An **invalid email** occurs when you attempt to send to an email address that is formatted in a manner that does not meet internet email format standards. Examples include addresses without the "@" sign, addresses that include certain special characters, or spaces in an address. This response comes from our own server, since an invalid email is impossible to even attempt to send to its [non-existent] destination.

[View your list of Invalid Emails](http://sendgrid.com/invalidEmail "Invalid Emails")


{% anchor h3 %} Blocks {% endanchor %}


If you receive a block notification, this means that the IP address from which you are sending has been placed on a black list of some sort. ISPs and organizations work from various blacklists, some of which are reputable and valid. In the event that you are placed on a blacklist, SendGrid will contact the ISP in question on your behalf and submit your IP for removal, once we've determined that your email are in fact legitimate and appropriate.

[View your list of Blocks](http://sendgrid.com/blocks)


{% anchor h3 %} Deferrals {% endanchor %}


A deferral occurs when an ISP is for some reason not ready to accept email from your IP address. Instead of blocking or bouncing the message, the ISP will defer receiving the message and wait for the email to be resent. An ISP may do this because it does not recognize the IP from which a message originates; or it could just be that their system is operating in such a way that they cannot accept the email at that specific time. If, upon your resending, the ISP determines that it is ready to trust you as a sender or their system operations are back to normal, the email will be accepted as normal. SendGrid will retry delivery of a deferred email on behalf of our customers for 72 hours from the time of the first deferral, after which time the email address is placed on the Hard Bounce list. If you have built your own email solution, you will want to build this intelligence into your code in order to avoid having to retry deliveries manually.


{% anchor h3 %} Drops {% endanchor %}


In certain cases, SendGrid will "Drop" a message to a specific email address in order to protect your sender reputation. SendGrid keeps [Email Lists](http://sendgrid.com/bounces/) to track bounces, spam reports, and unsubscribes for each of our users. If a user sends a message to an email address that exists on one of these lists within their account, SendGrid will automatically drop the message (i.e., not send to the address). \*Note: SendGrid users can always delete entries from these lists if an email address is erroneously placed on one or more of these lists, you can accomplish this by mousing over the entry and clicking the "Delete" button.


{% anchor h2 %} Advanced Statistics {% endanchor %}
 
{% info %} These stats are in beta. Data may be delayed by up to 10 hours. The top of these reports will indicate the last time the data was updated. {% endinfo %}
 
{% anchor h3 %} ISP {% endanchor %}


The [ISP report](http://sendgrid.com/statistics/isp) highlights how your mail performs across all the major ISPs, such as Hotmail, Yahoo, Gmail, etc.


{% anchor h3 %} Geography {% endanchor %}


[The geographical report](http://sendgrid.com/statistics/geo) shows a map of where your emails are being opened and clicked around the world.


{% anchor h3 %} Device {% endanchor %}


[The device report](http://sendgrid.com/statistics/devices) breaks down which devices are most frequently being used to open your mail.

Available devices:

|Device|Description|
|:-----|:----------|
|Desktop|Email software on desktop computer I.E. Outlook, Sparrow, or Apple Mail.|
|WebMail|A web-based email client I.E. Yahoo, Google, AOL, or Outlook.com.|
|Phone|A smart phone; IPhone, Android, Blackberry, etc.|
|Tablet|A tablet computer: IPad, android based tablet, etc.|
|Other|An unrecognized Device.|


{% anchor h3 %} Browser {% endanchor %}


[The browser report](http://sendgrid.com/statistics/browsers) shows which browsers are most frequently clicking links in your mail.


{% info %} There are similarities between Device and Browser statistics and are working on ways to consolidate the data. The current reasoning for two separate reports is that in some cases an open from a device can result with a click from a browser that represents the device (e.g. Open on an Iphone -\> Click on an Iphone), in other cases an open from one device can result in a click from a different browser (e.g. an Open on a desktop computer -\> Click on FireFox). {% endinfo %}

