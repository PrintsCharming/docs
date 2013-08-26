Hi! -name-  
 How are you?  

""" msg = EmailMultiAlternatives(subject, text\_content, fromEmail, [toEmail], headers={"X-SMTPAPI": hdr.asJSON()}) msg.attach\_alternative(html, "text/html") msg.send() {% endcodeblock %}
