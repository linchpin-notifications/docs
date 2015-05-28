---
layout: page
title: Notifications Documentation
permalink: /
---

## Writing a new Notification

LinchPin Notifications have a few components:
* A commands.json file that lists and describes the `commands` the notification supports
* A notification.json file that describes the notification, gives it a logo, and adds it to our app for users to choose.

### commands.json file

Example commands.json configuration file:
{% gist 9cb479365e50e1003ed4 %}

### notification.json file
{% highlight javascript %}
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
