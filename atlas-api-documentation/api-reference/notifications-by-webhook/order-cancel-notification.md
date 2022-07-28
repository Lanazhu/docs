# Order Cancel Notification

### Order Cancel Webhook

Webhooks are used to automatically receive notifications of events that happen.&#x20;

Once an event of "<mark style="color:green;">order.cancel</mark>" is received on the server, it can be processed and action taken as required.

Sometimes the airline might decline the pass through credit card and fail the booking, in this case, Atlas will give you a notification about it and cancel this order as well.

EndPoint ： The URL you configured to receive notifications&#x20;

Method : Post

{% tabs %}
{% tab title="Schema" %}
*   #### cid                                  <mark style="color:blue;">string</mark>                                                                                                &#x20;

    Identifier of client and user.
*   #### type                               <mark style="color:blue;">string</mark>                                                                                                 &#x20;

    Notification type.
* #### data                                                                                                                                                              <mark style="color:blue;"></mark>                                                                                      &#x20;
  *   #### orderNo                                  <mark style="color:blue;">string</mark>                                                                      &#x20;

      Order number
  *   #### orderStatus                           <mark style="color:blue;">int</mark>                                                                            &#x20;

      orderStatus=-3 means cancelled
  *   #### errorCode                               <mark style="color:blue;">string</mark>

      please check the definition of errorCode here
  *   #### errorMessage                       <mark style="color:blue;">string</mark>                                                                      &#x20;

      Error message
{% endtab %}

{% tab title="Samples" %}
```json
{
    "cid": "pxmhg93103",
    "type": "order.cancel",
    "data": {
      "orderNo": "BCNQL20201031184148568",
      "orderStatus": -3, 
      "errorCode": "604",
      "errorMessage": "Payment declined by airline"
    }
}
```
{% endtab %}
{% endtabs %}
