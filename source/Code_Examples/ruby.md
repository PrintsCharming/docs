--- layout: page weight: 0 title: Ruby navigation: show: true ---

This example shows how to send email plain text and HTML email using
Ruby. The gem [Mail](https://github.com/mikel/mail) is required.

{% codeblock lang:ruby %} require 'mail' Mail.defaults do
delivery\_method :smtp, { :address =\> "smtp.sendgrid.net", :port =\>
587, :domain =\> "yourdomain.com", :user\_name =\>
"yourusername@domain.com", :password =\> "yourPassword", :authentication
=\> 'plain', :enable\_starttls\_auto =\> true } end mail = Mail.deliver
do to 'yourRecipient@domain.com' from 'Your Name <name@domain.com>'
subject 'This is the subject of your email' text\_part do body 'Hello
world in text' end html\_part do content\_type 'text/html;
charset=UTF-8' body '**Hello world in HTML**' end end {% endcodeblock %}
To install the [Mail](https://github.com/mikel/mail) gem please note
that you need the OpenSSL library installed, then run the following: {%
codeblock lang:bash %} gem install mail {% endcodeblock %}
