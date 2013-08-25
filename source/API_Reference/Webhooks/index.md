---
layout: page
weight: 100
title: Webhooks Overview
navigation:
  show: true
---

Webhooks are an easy way to get push notifications. A webhook is like an API endpoint but inverted; instead of making a call to our API, you define a callback URL to which we will HTTP POST information as things happen. Your callback URL can then execute code based on the POSTs. You can think of it as defining an API endpoint for your app that will receive output from SendGrid.

We currently have two Webhooks available. The [Event Webhook](event.html) will POST when an email event occurs, such as a bounce or an unsubscribe. The [Inbound Parse Webhook](parse.html) will receive emails and then post their constituent components (e.g. subject, body, and attachments) to your URL.


{% anchor h2 %} Debugging {% endanchor %}


We offer a utility for capturing and inspecting webhook posts. Check it out at [http://hookdebug.sendgrid.com/](http://hookdebug.sendgrid.com/).


{% anchor h2 %} Caveats {% endanchor %}


Keep in mind that your servers need to be robust enough to handle a large number of requests from SendGrid's webhooks, especially if you send or receive a lot of email. We offer a [free load testing service](http://loader.io), loader.io, that you can use to test your servers.
