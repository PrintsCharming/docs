---
layout: page
weight: 0
title: Apps (Filters)
navigation:
  show: true
---

Following are the apps that can be specified in the filters section of the X-SMTPAPI header. All filters and setting names must be lowercase.

Please note that if a filter is not specified as being either disabled or enabled in the X-SMTPAPI header, it will default to the state of the app in the "Apps" tab on the website.


{% warning %} If you're enabling an App, also called a filter, via SMTPAPI, you are required to define all the parameters for the App. If you have the App disabled on the web interface, our system will not pull the settings for the disabled app when you dynamically enable it. For instance, if you have a template designed but disabled, you can't just enable it via the API; you need to define the template in the API call itself. {% endwarning %}


For more information on the utility of these apps, please check out the [Apps]({{root_url}}/Apps/) section.

### Filter - 'gravatar':

Inserts an img tag at the bottom of the html section of an e-mail to display the gravatar associated with the mail sender.



* * * * *

### Filter - 'clicktrack':

Rewrites links in e-mail text and html bodies to go through our webservers, allowing for tracking when a link is clicked on.



* * * * *

### Filter - 'subscriptiontrack':

Inserts a subscription management link at the bottom of the text and html bodies. Custom text is set in the settings, with the subscription management link being substituted into the text either as '% %' for plain text bodies, and as a link where the text in between the '%' and '%' is the link text.



* * * * *

### Filter - 'opentrack':

Inserts an `` tag at the bottom of the html section of an e-mail which will be used to track if an e-mail is opened.



* * * * *

### Filter - 'footer':

Inserts a footer at the bottom of the text and HTML bodies.



* * * * *

### Filter - 'spamcheck':

Tests message with SpamAssassin to determine if it is spam, and drop it if it is.



* * * * *

### Filter - 'ganalytics':

Re-writes links to integrate with Google Analytics.



* * * * *

### Filter - 'domainkeys':

Allows you to specify the domain to use to sign messages with Domain Keys. This domain should match the domain in the From address of your e-mail. For more info, check out these [details on Domain Keys.]({{root_url}}/Apps/domain_keys.html)



* * * * *

### Filter - 'dkim':

Allows you to specify the domain to use to sign messages with DKIM certification. This domain should match the domain in the From address of your e-mail. For more info, check out these [details on DKIM.]({{root_url}}/Apps/dkim.html)



* * * * *

### Filter - 'template':

Wraps a template around your email content. Useful for sending out marketing email and other nicely formatted messages.



* * * * *

### Filter - 'bcc':

Sends a BCC copy of the email created in this transaction to the address specified.



* * * * *

### Filter - 'forwardspam':

Allows for a copy of spam reports to be forwarded to an email address.



* * * * *

### Filter - 'bypass\_list\_management':

Some emails are too important to do normal list management checks, such as password resets or critical alerts. Enabling this filter will bypass the normal unsubscribe / bounce / spam report checks and queue the e-mail for delivery.



