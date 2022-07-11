# Register Webhook

## Overview

In this guide, you'll learn how to set up and handle webhooks in your integration.&#x20;

After you've set up webhooks, you'll receive notifications about events that happen in your account - for example, when an airline has a schedule change affecting one of your orders.&#x20;

We'll send these events to your server, and then you can process them and take action automatically - for example updating your database or emailing a customer.

## End Point

[https://sandbox.atlaslovestravel.com/updateWebhookURL.do](https://sandbox.atlaslovestravel.com/updateWebhookURL.do)

## Request

{% tabs %}
{% tab title="Schema" %}
*   #### cid                          <mark style="color:blue;">string</mark>                                                                                                 <mark style="color:green;">Required</mark>

    Identifier of client and user.
*   #### url                           <mark style="color:blue;">string</mark>                                                                                                 <mark style="color:green;">Required</mark>

    The url address to receive webhook message.
{% endtab %}

{% tab title="Sample" %}
```json
{
    "cid": "XXXXXXXX",
    "url": "https://xxx.com/xxxx"
}
```
{% endtab %}
{% endtabs %}

## Response

{% tabs %}
{% tab title="Schema" %}
*   #### status                                  <mark style="color:blue;">int</mark>                                                                                                       <mark style="color:green;">Required</mark>

    0: success

    2: System error
*   #### msg                                      <mark style="color:blue;">string</mark>                                                                                                 <mark style="color:green;">Required</mark>

    Error message.
{% endtab %}

{% tab title="Sample" %}
```json
{
    "status": 0,
    "msg": "success"
}
```
{% endtab %}
{% endtabs %}



