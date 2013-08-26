Hi! -name-  
 How are you?  

""" msg = EmailMultiAlternatives(subject, text_content, fromEmail, [toEmail], headers={"X-SMTPAPI": hdr.asJSON()}) msg.attach_alternative(html, "text/html") msg.send() {% endcodeblock %}
