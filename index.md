---
layout: page
title: Notifications Documentation
permalink: /
---

## Writing a new Notification

LinchPin Notifications have a few components:
* A <span class="badge">commands.json</span> file that lists and describes the `commands` the notification supports
* A <span class="badge">notification.json</span> file that describes the notification, gives it a logo, and adds it to our app for users to choose.

### commands.json file

The commmands.json file describes the different commands your notification supports. The keys of the json object are the command names. Each key has an object that is a [json schema](http://json-schema.org/) of the Configuration required to run the command.

For instance, an example commands.json configuration file could be:
{% gist 9cb479365e50e1003ed4 %}

In these `Email` notification example the commands are `sendEmail` and `sendEmailHandleBars`, and the json schema for a `sendEmail` command is:
{% highlight javascript %}
{
    "title":"Send an Email",
    "description":"Sends an Email using LinchPin's infrastructure",
    "properties":{
      "email": {
        "$ref":"#/definitions/email"
      }
    }
}
{% endhighlight %}

LinchPin's notifications API will automatically wrap these configuration schema's and the resulting schema will look something like:

{% highlight javascript %}
{
  "title": "email code command schema",
  "LpConfig": "NotificationConfiguration",
  "type": "object",
  "properties": {
    "name": {
      "type": "string"
    },
    "notification": {
      "enum": [
        "email"
      ]
    },
    "command": {
      "enum": [
        "code"
      ]
    },
    "config": "ResourceNotFound"
  },
  "required": [
    "notification",
    "name",
    "command",
    "config"
  ],
  "additionalProperties": false
}
{% endhighlight %}

### notification.json file
{% highlight javascript linenos %}
{
    "name": "email",
    "label": "Email",
    "description": "Email notification",
    "private": true,
    "form_options": null,
    "is_oauth": false,
    "logo": "//linchpin-web-assets.s3.amazonaws.com/v1/notifications/email/email-logo.png",
    "server_notification": true
}
{% endhighlight %}

<div class="alert alert-danger"><b>Warning!</b> Including an id will replace default behavior. </div>

## Write some docs @justjico !


Testing writing `something` ...
