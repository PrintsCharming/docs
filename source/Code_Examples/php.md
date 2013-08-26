---
layout: page
weight: 0
title: PHP
navigation:
  show: true
---

This library allows you to quickly and easily send emails through SendGrid using PHP.


{% anchor h2 %} How To Install The Libraries {% endanchor %}
 {% codeblock %} git clone git://github.com/sendgrid/sendgrid-php.git {% endcodeblock %} 
{% anchor h2 %} SendGrid APIs {% endanchor %}


SendGrid provides two methods of sending email: the Web API, and SMTP API. SendGrid recommends using the SMTP API for sending emails. For an explanation of the benefits of each, refer to the [integration page](/Integrate/index.html).

This library implements a common interface to make it very easy to use either API.


{% anchor h2 %} Mail Pre-Usage {% endanchor %}


Before we begin using the library, its important to understand a few things about the library architecture. First, the SendGrid Mail object is the means of setting mail data. In general, data can be set in following three ways for most elements:

-   **set** - reset the data, and initialize it to the given element. This will destroy previous data.
-   **set (List)** - for array based elements, we provide a way of passing the entire array in at once. This will also destroy previous data.
-   **add** - append data to the list of elements.

Sending an email is as simple as:

1.  Creating a SendGrid Instance
2.  Creating a SendGrid Mail object, and setting its data
3.  Sending the mail using either SMTP API or Web API.


{% anchor h2 %} Mail Usage {% endanchor %}


To begin using this library, you must first include it in your code, like so:

{% codeblock lang:php %} <?php include "path/to/sendgrid-php/SendGrid_loader.php" ; ?> {% endcodeblock %}

Then, initialize the SendGrid object with your SendGrid credentials:

{% codeblock lang:php %} <?php $sendgrid="new" sendgrid('username', "password" ); ?> {% endcodeblock %}

Create a new SendGrid Mail object and add your message details, as follows:

{% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('foo@bar.com')-\> setFrom('me@bar.com')-\> setSubject('Subject goes here')-\> setText('Hello World!')-\> setHtml('**Hello World!**'); ?\> {% endcodeblock %}

Finally, send it using the API of your choice of SMTP like so:

{% codeblock lang:php %} <?php $sendgrid- ?> smtp-\> send(\$mail); ?\> {% endcodeblock %}

Or you can send it using the Web API like so:

{% codeblock lang:php %} <?php $sendgrid- ?> web-\> send(\$mail); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Categories {% endanchor %}


Categories are used to group email statistics provided by SendGrid. To use a category, simply set the category name.


{% info %} There is a maximum of 10 categories per email. {% endinfo %}
 {% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('foo@bar.com')-\> ... addCategory("Category 1")-\> addCategory("Category 2"); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Attachments {% endanchor %}


Attachments are currently file based only, with future plans for an in memory implementation as well.


{% info %} File attachments are limited to 7 MB per file. {% endinfo %}
 {% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('foo@bar.com')-\> ... addAttachment("../path/to/file.txt"); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Substitutions {% endanchor %}


Substitutions can be used to customize multi-recipient emails, and tailor them for the user.

{% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('john@somewhere.com')-\> addTo("harry@somewhere.com")-\> addTo("Bob@somewhere.com")-\> ... setHtml("Hey %name%, we've seen that you've been gone for a while")-\> addSubstitution("%name%", array("John", "Harry", "Bob")); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Sections {% endanchor %}


Sections can be used to further customize messages for the end users. A section is only useful in conjunction with a substition value.

{% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('john@somewhere.com')-\> addTo("harry@somewhere.com")-\> addTo("Bob@somewhere.com")-\> ... setHtml("Hey %name%, you work at %place%")-\> addSubstitution("%name%", array("John", "Harry", "Bob"))-\> addSubstitution("%place%", array("%office%", "%office%", "%home%"))-\> addSection("%office%", "an office")-\> addSection("%home%", "your house"); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Unique Arguments {% endanchor %}


Unique Arguments can be used for tracking purposes and developing data for unique statistical analysis.

{% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('foo@bar.com')-\> ... addUniqueArgument("Customer", "Someone")-\> addUniqueArgument("location", "Somewhere"); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Filter Settings {% endanchor %}


Filter Settings are used to enable and disable apps, and to pass parameters to those apps.

{% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('foo@bar.com')-\> ... addFilterSetting("gravatar", "enable", 1)-\> addFilterSetting("footer", "enable", 1)-\> addFilterSetting("footer", "text/plain", "Here is a plain text footer")-\> addFilterSetting("footer", "text/html", "Here is an HTML footer"); ?\> {% endcodeblock %} 
{% anchor h3 %} Using Headers {% endanchor %}


Headers can be used to add existing sendgrid functionality (such as for categories or filters), or custom headers can be added as necessary.

{% codeblock lang:php %} <?php $mail="new" sendgrid\mail(); $mail- ?> addTo('foo@bar.com')-\> ... addHeader("category", "My New Category"); ?\> {% endcodeblock %}
