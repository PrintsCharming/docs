--- layout: page weight: 100 title: API Reference Index navigation:
show: true --- {% anchor h2 %} Send Email {% endanchor %}

There are three different technical concepts you should know about
SendGrid related to sending email:

### SMTP

This is a protocol rather than an API. SMTP is widely supported by
applications and is usually the fastest way to integrate with SendGrid.
[Learn how to integrate using SMTP]({{root_url}}/Integrate/index.html).

### Web Email API

If SMTP is not used, we also offer a simple [Web API mail
method]({{root_url}}/API_Reference/Web_API/mail.html) to send email.

### SMTPAPI

This is an API that allows you to tag your emails to get detailed
statistics on each tag, send multiple customized emails in one request
via mail merge, and configure each app on a per email basis. This is
done by passing a JSON string in the X-SMTPAPI header if using SMTP or
in the x-smtpapi HTTP parameter if using the web API. [Using the SMTP
API]({{root_url}}/API_Reference/SMTP_API/index.html)

{% anchor h2 %} Configure Service or Retrieve Information {% endanchor
%}

SendGrid has a Web API that allows customers to retrieve information
about their account such as statistics, bounces, spam reports,
unsubscribes, and other information. In addition, the Web API allows
customers to create sub-accounts and control the settings of these
accounts for an OEM setup. See the [list of Web API
calls]({{root_url}}/API_Reference/Web_API/index.html).

{% anchor h2 %} Receive Email {% endanchor %}

SendGrid can parse the email bodies and attachments from incoming emails
and post them to your web application. For details on how to integrate
your application to start receiving emails please refer to our [Parse
Webhook]({{root_url}}/API_Reference/Webhooks/parse.html). Application
examples include:

-   Posting blog articles via email
-   Processing email replies in a mailing list
-   Allowing users to upload pictures to their profile via email
-   Submit support requests via email

{% anchor h2 %} Real-time Event Notification Webhook {% endanchor %}

SendGrid can send real-time notifications about events that happen on
the SendGrid system to a URL. These events include clicks, opens,
unsubscribe, bounces, and many others. These events include more data
than what SendGrid records and allow customers to customize their own
reporting. What makes this API even more powerful is the ability to
include user-defined parameters in each event. Through our SMTP API,
customers can embed unique parameters in each email they send. These
parameters are then passed to each event notification so your
application can associate these events with your customers. Read more
about the [Event
Webhook]({{root_url}}/API_Reference/Webhooks/event.html). Examples of
applications include:

-   Associate a spam report with a specific campaign and user in your
    application
-   Know real-time when a user has clicked on a confirmation email
-   Get the specific link clicked on an email
-   Get the browser version used by a customer
-   Know the specific MTA response for a customer

