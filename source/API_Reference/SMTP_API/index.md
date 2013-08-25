---
layout: page
weight: 100
title: SMTP API Overview
navigation:
  show: true
---

SendGrid's SMTP API allows developers to specify custom handling instructions for e-mail. This is accomplished through a header, X-SMTPAPI, that is inserted into the message. The header is a JSON encoded list of instructions and options for that email. An example header looks like this:

{% codeblock lang:javascript %}
{
  "category": "newuser"
}
{% endcodeblock %}

In this case, the header is telling the processing routine to assign this email the [category]({{root_url}}/Delivery_Metrics/categories.html) of "newuser".


{% anchor h2 %} The X-SMTPAPI Header {% endanchor %}


The X-SMTPAPI header is a JSON-encoded associative array consisting of several sections, below are examples of JSON strings using each section. This header can be added to any SMTP message sent to SendGrid and the instructions in the header will be interpreted and applied to that message's transcation.

To: An array of addresses to send the message to, optionally including the display name.

{% codeblock lang:javascript %}
{
  "to": [
    "<ben@example.com>",
    "Joe Smith <joe@example.com>"
  ]
}
{% endcodeblock %}

[Substitution]({{root_url}}/API_Reference/SMTP_API/substitution_tags.html): An associative array of substitution tags, where each tag is associated with a list of replacement text for the tag in the body text. Each Substitution value corresponds to an email in the "To" section of the JSON string.

{% codeblock lang:javascript %}
{
  "sub": {
    "%name%": [
      "Ben",
      "Joe"
    ],
    "%role%": [
      "%sellerSection%",
      "%buyerSection%"
    ]
  }
}
{% endcodeblock %}

[Section]({{root_url}}/API_Reference/SMTP_API/section_tags.html): Sections can be used to simplify substitution values that are common to many recipients. This is an associative array of sections that can be used in substitution values.

{% codeblock lang:javascript %}
{
  "section": {
    "%sellerSection%": "Seller information for: %name%",
    "%buyerSection%": "Buyer information for: %name%"
  }
}
{% endcodeblock %}

[Category]({{root_url}}/Delivery_Metrics/categories.html): Associates the category of email this should be logged as. You may insert up to 10 categories as an array, these categories are not predefined.

{% codeblock lang:javascript %}
{
  "category": [
    "category1",
    "category2"
  ]
}
{% endcodeblock %}

[Unique Arguments]({{root_url}}/API_Reference/SMTP_API/unique_arguments.html): An associative array of arguments and their values to be applied to all emails sent in this SMTP API transaction.

{% codeblock lang:javascript %}
{
  "unique_args": {
    "orderNumber": "12345",
    "eventID": "6789"
  }
}
{% endcodeblock %}

[Apps]({{root_url}}/API_Reference/SMTP_API/apps.html): An associative array of filters and their settings, used to override filter settings already setup for your account. Settings are an associative array of the setting names and their values.

{% codeblock lang:javascript %}
{
  "filters": {
    "footer": {
      "settings": {
        "enable": 1,
        "text/plain": "Thank you for your business"
      }
    }
  }
}
{% endcodeblock %} All of the above examples can then be combined into one larger JSON string placed in a header named X-SMTPAPI, and would look like this: {% codeblock lang:javascript %}
{
  "to": [
    "ben@sendgrid.com",
    "joe@sendgrid.com"
  ],
  "sub": {
    "%name%": [
      "Ben",
      "Joe"
    ],
    "%role%": [
      "%sellerSection%",
      "%buyerSection%"
    ]
  },
  "section": {
    "%sellerSection%": "Seller information for: %name%",
    "%buyerSection%": "Buyer information for: %name%"
  },
  "category": "Orders",
  "unique_args": {
    "orderNumber": "12345",
    "eventID": "6789"
  },
  "filters": {
    "footer": {
      "settings": {
        "enable": 1,
        "text/plain": "Thank you for your business"
      }
    }
  }
}
{% endcodeblock %}

The above example is formatted for readability. Headers must be wrapped to keep the line length under 72. By RFC 821 no line can be longer than 1,000, so if you are going to generate this string yourself it is a good idea to make sure that you wrap it.

Here is a full example of generating the above JSON header in a Perl script:

{% codeblock lang:perl %} \#!/usr/bin/perl use strict; use JSON; my \$header = { to =\> ['ben@sendgrid.com', 'joe@sendgrid.com], sub =\> { '%name%' =\> [ 'Ben', 'Joe' ], '%role%' =\>; [ 'sellerSection', 'buyerSection' ] }, section =\> { '%sellerSection%' =\>; 'Seller information for: %name%', '%buyerSection%' =\> 'Buyer information for: %name%' }, category =\> 'Orders', unique\_args =\> { 'orderNumber' =\> '12345', 'eventID' =\> '6789' }, filters =\> { 'footer' =\> {'settings' =\> {'text/plain' =\> "Thank you for your business"}}}}; my \$json = JSON-\>new; \$json-\>space\_before(1); \$json-\>space\_after(1); my \$js = \$json-\>encode(\$header); \# This regex breaks the string up at whitespaces to keep the line length short \$js =\~ s/(.{1,72})(\\s)/\$1\\n   /g; my \$hdr = "X-SMTPAPI: \$js"; print "\$hdr\\n"; {% endcodeblock %} 
{% anchor h2 %} Requirements and Limitations {% endanchor %}


When setting filters via SMTPAPI, all filter names and setting names must be lowercase.

If you use the multiple recipient functionality of the API, you must not send to multiple recipients with the SMTP protocol as well. Doing so can cause duplicates of the message to be sent.

Ensure that the header is limited to a maximum total line length of 1,000 characters. Failure to do this can cause intermediate MTA's to split the header for you on non-space boundaries, which will cause spaces to be inserted in the final resulting e-mail. In addition, if your e-mail is going through another MTA before reaching SendGrid, it is likely to have an even lower setting for maximum header length and may truncate the header.

When using the API, if our system encounters a parsing error, the message will be bounced to the address specified in the MAIL FROM portion of the SMTP session. The MAIL FROM address is re-written when we send e-mail out for final delivery, so it is safe to set this to an address that can receive the bounces so that you will be alerted on errors.

While there is no hard limit to the number of addresses that can be sent to in a multiple recipient e-mail, it is best to split up large jobs at around 1,000 recipients, as this will better allow for the processing load to be distributed.

For substitution tags, it is best to avoid characters that have special meaning in html, such as \<,\>, and &. These might end up encoded and will not be properly substituted.
