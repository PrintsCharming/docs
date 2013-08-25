---
layout: page
weight: 0
title: CodeIgniter
navigation:
  show: true
---

CodeIgniter comes with an email sending library built in. See more information on how to [use CodeIgniter with SendGrid](http://codeigniter.com/user_guide/libraries/email.html).


{% info %} It is important to use the correct end of lines using "crlf" =\> "\\r\\n" and "newline" =\> "\\r\\n". {% endinfo %}
 {% codeblock lang:php %} <?php $this- ?>load-\>library('email'); \$this-\>email-\>initialize(array( 'protocol' =\> 'smtp', 'smtp\_host' =\> 'smtp.sendgrid.net', 'smtp\_user' =\> 'sendgridusername', 'smtp\_pass' =\> 'sendgridpassword', 'smtp\_port' =\> 587, 'crlf' =\> "\\r\\n", 'newline' =\> "\\r\\n" )); \$this-\>email-\>from('your@example.com', 'Your Name'); \$this-\>email-\>to('someone@example.com'); \$this-\>email-\>cc('another@another-example.com'); \$this-\>email-\>bcc('them@their-example.com'); \$this-\>email-\>subject('Email Test'); \$this-\>email-\>message('Testing the email class.'); \$this-\>email-\>send(); echo \$this-\>email-\>print\_debugger(); ?\> {% endcodeblock %}
