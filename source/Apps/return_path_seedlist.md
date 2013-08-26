---
layout: page
weight: 0
title: Return Path Seedlist
navigation:
  show: true
---

{% info %} This App is only available to customers who are Return Path certified. {% endinfo %}
 {% xmljsontabs %} ![]({{root_url}}/images/return_path_seedlist.png "RP-fixed")

The Return Path Seedlist App allows customers to easily use Return Path's Mailbox Monitor feature to send email to a Seedlist of top recipient servers and examine delivery rates across that list. The seed list covers more than 130 domains including the top ISPs in the U.S., European, Canadian, Latin American and Asia Pacific markets. The list itself will be provided by Return Path.


{% anchor h2 %} Settings {% endanchor %}


<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Name</th>
         <th>Required</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Global Frequency</td>
         <td>No</td>
         <td>If you are not using subject based keywords, select this option.</td>
      </tr>
      <tr>
         <td>Use Lists</td>
         <td>No</td>
         <td>Select this option to specify subjects that will be used to identify this category of message.</td>
      </tr>
      <tr>
         <td>Frequency</td>
         <td>Yes</td>
         <td>The number of times per day the Seedlist should be used.</td>
      </tr>
      <tr>
         <td>Email List</td>
         <td>Yes</td>
         <td>The addresses in the Seedlist.</td>
      </tr>
   </tbody>
</table>



