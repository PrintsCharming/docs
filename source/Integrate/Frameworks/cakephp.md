---
layout: page
weight: 0
title: CakePHP
navigation:
  show: true
---

CakePHP comes with an email library that already supports SMTP. [For more information check out the CakePHP documentation page](http://book.cakephp.org/view/1286/Sending-a-basic-message). This example shows how to send an email with both HTML and text bodies.

In **app/views/layouts/** you need to define the layout of your text and HTML emails: {% codeblock %}
email/ html/ default.ctp text/ default.ctp
{% endcodeblock %} In **app/views/layouts/email/text/default.ctp** add: {% codeblock lang:php %} <!--?php echo $content_for_layout; ?--> {% endcodeblock %} and in **app/views/layouts/email/html/default.ctp** add: {% codeblock lang:php %} <!--?php echo $content_for_layout; ?--> {% endcodeblock %} Then create the template for your emails. In this example we created templates for a registration email with the following structure: {% codeblock %}
app/ views/ elements/ email/ text/ registration.ctp html/ registration.ctp
{% endcodeblock %} In **app/views/elements/email/text/registration.ctp** add: {% codeblock lang:php %} Dear <!--?php echo $name ?-->, Thank you for registering. Please go to http://domain.com to finish your registration. {% endcodeblock %} and in **app/views/layouts/email/html/default.ctp** add: {% codeblock lang:php %} Dear <!--?php echo $name ?-->, Thank you for registering. Please go to [here](http://domain.com) to finish your registration. {% endcodeblock %} In your controller enable the email component:  
  
 {% codeblock lang:php %} <!--?php var $components = array('Email'); ?--> {% endcodeblock %} Then anywhere in your controller you can do something like the following to send an email: {% codeblock lang:php %} <?php $this- ?>Email-\>smtpOptions = array( 'port'=\>'587', 'timeout'=\>'30', 'host' =\> 'smtp.sendgrid.net', 'username'=\>'sendgrid\_username', 'password'=\>'sendgrid\_password', 'client' =\> 'yourdomain.com' ); \$this-\>Email-\>delivery = 'smtp'; \$this-\>Email-\>from = 'Your Name '; \$this-\>Email-\>to = 'Recipient Name '; \$this-\>set('name', 'Recipient Name'); \$this-\>Email-\>subject = 'This is a subject'; \$this-\>Email-\>template = 'registration'; \$this-\>Email-\>sendAs = 'both'; \$this-\>Email-\>send(); ?\> {% endcodeblock %}
