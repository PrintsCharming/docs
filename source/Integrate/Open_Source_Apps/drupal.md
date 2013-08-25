--- layout: page weight: 0 title: Drupal navigation: show: true ---

To use SendGrid with [Drupal](http://drupal.org/ "Drupal"), use the
[SMTP Authentication Support
module](http://drupal.org/project/smtp "SMTP Authentication Support").
Install a version of this module that is compatible with your version of
Drupal.

![]({{root_url}}/images/drupal_1.png "SMTP Module")

Open your modules page, find the SMTP module, and configure it with the
following settings:

-   **SMTP Server** - smtp.sendgrid.net
-   **SMTP Port** - 587
-   **Use Encrypted Protocal** - No. If you want encryption choose "Use
    SSL" and set SMTP Port to 465
-   **Username** - SendGrid Username
-   **Password** - SendGrid Password

![]({{root_url}}/images/drupal_2.png "SMTP Module Configuration")
