---
layout: page
title: Notifications Documentation
permalink: /
---

## Writing a new Notification

LinchPin Notifications have a few components:
* A commands.json file that lists and describes the `commands` the notification supports
* A notification.json file that describes the notification, gives it a logo, and adds it to our app for users to choose.

### Commands.json file

Example commands.json configuration file:
```javascript
{
  "sendEmail":{
    "title":"Send an Email",
    "description":"Sends an Email using LinchPin's infrastructure",
    "properties":{
      "email": {
        "$ref":"#/definitions/email"
      }
    }
  },
  "sendEmailHandlebars":{
    "title":"Send an Email using a HandleBars template",
    "description":"Sends an Email using LinchPin's infrastructure. The body variable is a HandlerBars template and it renders event data passed in.",
    "properties":{
      "email": {
        "$ref":"#/definitions/email"
      }
    }
  },
  ".definitions":{
    "email": {
      "type": "object",
      "title": "Email Definition",
      "description": "Config for sending an email",
      "LpConfig": "Notifications/email",
      "properties": {
        "recipients": {
          "$ref": "../Email"
        },
        "body": {
          "type": "string"
        },
        "subject": {
          "type": "string"
        }
      },
      "required": [
        "recipients",
        "body",
        "subject"
      ],
      "additionalProperties": false
    }
  }
}
```
<div class="alert alert-danger"><b>Warning!</b> Including an id will replace default behavior. </div>

## Write some docs @justjico !


Testing writing `something` ...
