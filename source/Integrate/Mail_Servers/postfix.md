---
layout: page
weight: 0
title: Postfix
navigation:
  show: true
---

Updating the Postfix configuration to use SendGrid as a relay host is easy. For more advanced configuration scenarios, you'll need to refer to the Postfix documentation.

Find your Postfix config file, typically **/etc/postfix/main.cf**, and add the following:

{% codeblock %}
smtp_sasl_auth_enable = yes smtp_sasl_password_maps = static:yourSendGridUsername:yourSendGridPassword smtp_sasl_security_options = noanonymous smtp_tls_security_level = may start_tls = yes header_size_limit = 4096000 relayhost = [smtp.sendgrid.net]:587
{% endcodeblock %} Make sure to restart Postfix: {% codeblock lang:bash %} \$ /etc/init.d/postfix restart {% endcodeblock %} 
{% info %} If you are getting ***no mechanism available*** error messages it generally indicates that you are missing some SASL authentication libraries. {% endinfo %}


Install the missing module dependency using apt-get (i.e., Debian, Ubuntu):

{% codeblock lang:bash %} \$ apt-get install libsasl2-modules {% endcodeblock %} Or using a yum (i.e., RedHat, Fedora, CentOS): {% codeblock lang:bash %} \$ yum install cyrus-sasl-plain {% endcodeblock %}
