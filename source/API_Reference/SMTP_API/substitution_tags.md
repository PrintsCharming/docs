Hello -name-,  
 Thank you for your interest in our products. I have set up an appointment to call you at -time- EST to discuss your needs in more detail. If you would like to reschedule this call please visit the following link: [reschedule](http://sendgrid.com/reschedule?id=-customerID-) Regards, -salesContact- -contactPhoneNumber-  

{% endcodeblock %}

An accompanying SMTP API JSON header might look something like this:

{% codeblock lang:javascript %}
{
  "to": [
    "john.doe@gmail.com",
    "jane.doe@hotmail.com"
  ],
  "sub": {
    "-name-": [
      "John",
      "Jane"
    ],
    "-customerID-": [
      "1234",
      "5678"
    ],
    "-salesContact-": [
      "Jared",
      "Ben"
    ],
    "-contactPhoneNumber-": [
      "555.555.5555",
      "777.777.7777"
    ],
    "-time-": [
      "3:00pm",
      "5:15pm"
    ]
  }
}
{% endcodeblock %}

The final email for John would look like this:

{% codeblock lang:html %}

Hello John,  
 Thank you for your interest in our products. I have set up an appointment to call you at 3:00pm EST to discuss your needs in more detail. If you would like to reschedule this call please visit the following link: [reschedule](http://sendgrid.com/reschedule?id=1234) Regards, Jared 555.555.5555  

{% endcodeblock %}
