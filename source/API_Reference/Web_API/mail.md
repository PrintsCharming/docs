---
layout: page
weight: 0
title: Mail
navigation:
  show: true
---

This endpoint allows you to send email.


{% anchor h2 %} send {% endanchor %}


Send email.


{% xmljsontabs mail %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="mail-json">
### Call: Send to One Recipient



{% codeblock %}
https://sendgrid.com/api/mail.send.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to=destination@example.com&toname=Destination&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}
<h3>Call: Send to Multiple Recipients
{% codeblock lang:bash %}
https://sendgrid.com/api/mail.send.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to[]=destination@example.com&toname[]=Destination&to[]=destination2@example.com&toname[]=Destination2&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="mail-xml">
### Call: Send to One Recipient



{% codeblock %}
https://sendgrid.com/api/mail.send.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to=destination@example.com&toname=Destination&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}
<h3>Call: Send to Multiple Recipients
{% codeblock lang:bash %}
https://sendgrid.com/api/mail.send.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&to[]=destination@example.com&toname[]=Destination&to[]=destination2@example.com&toname[]=Destination2&subject=Example_Subject&text=testingtextbody&from=info@domain.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   success
   <result>
</result>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>...</error>
      ...
   </errors>
   @nodes
</result>

{% endcodeblock %}




</div>
</div>

* * * * *

### cURL Examples

Send to one email recipient



{% codeblock lang:bash %}
$ curl -d 'to=destination@example.com&toname=Destination&subject=Example Subject&text=testingtextbody&from=info@domain.com&api_user=your_sendgrid_username&api_key=your_sendgrid_password' https://sendgrid.com/api/mail.send.json
{% endcodeblock %}



Send to multiple email recipients



{% codeblock lang:bash %}
$ curl -d 'to[]=destination@example.com&toname[]=Destination&to[]=destination2@example.com&toname[]=Destination2&subject=Example Subject&text=testingtextbody&from=info@domain.com&api_user=your_sendgrid_username&api_key=your_sendgrid_password' https://sendgrid.com/api/mail.send.json
{% endcodeblock %}



Send a test with attachment



{% codeblock lang:bash %}
$ curl https://sendgrid.com/api/mail.send.json \
-F to=recipient@domain.com -F toname=test -F subject="Example Subject" \
-F text="testing text body" --form-string html="<strong>testing html body</strong>" \
-F from=test@yourdomain.com -F api_user=your_sendgrid_username -F api_key=your_sendgrid_password \
-F files[attachment.gz]=@f.php.gz https://sendgrid.com/api/mail.send.json
{% endcodeblock %}



<span class="label label-info">Note</span> To ensure that it uploads from a local file, use \<@filename\>.

Send a test specifying the file content type by appending ';type=<mime type>' to the file name



{% codeblock lang:bash %}
$ curl https://sendgrid.com/api/mail.send.json \
-F to=recipient@domain.com -F toname=test -F subject="Example Subject" \
-F text="testing text body" --form-string html="<strong>testing html body</strong>" \
-F from=test@yourdomain.com -F api_user=your_sendgrid_username -F api_key=your_sendgrid_password \
-F files[attachment.pdf]=@attachment.pdf;type=application/pdf
{% endcodeblock %}



### Raw HTTP Dump

The following is a dump of the HTTP data sent to our server to generate an email via our web API.



{% codeblock %}
POST /api/mail.send.json HTTP/1.1
{% endcodeblock %}

{% codeblock %}
Host: sendgrid.com

Accept: */*

Content-Length: 999

Expect: 100-continue

Content-Type: multipart/form-data; boundary=----------------------------400f182a9360

HTTP/1.1 100 Continue

------------------------------400f182a9360

Content-Disposition: form-data; name="api_user"

YOURUSERNAME

------------------------------400f182a9360

Content-Disposition: form-data; name="api_key"

YOURKEY

------------------------------400f182a9360

Content-Disposition: form-data; name="to"

someone@somewhere.com

------------------------------400f182a9360

Content-Disposition: form-data; name="subject"

test of file sends

------------------------------400f182a9360

Content-Disposition: form-data; name="html"

the HTML

------------------------------400f182a9360

Content-Disposition: form-data; name="text"

the plain text

------------------------------400f182a9360

Content-Disposition: form-data; name="from"

example@sendgrid.com

------------------------------400f182a9360

Content-Disposition: form-data; name="files[myfile]"; filename="myfile"

Content-Type: application/octet-stream

file with stuff in it

------------------------------400f182a9360--

HTTP/1.1 200 OK

Server: nginx/0.7.65

Date: Fri, 03 Jun 2011 22:30:58 GMT

Content-Type: application/json

Transfer-Encoding: chunked

Connection: keep-alive

{% endcodeblock %}

 {% codeblock %} {"message":"success"} {% endcodeblock %}
