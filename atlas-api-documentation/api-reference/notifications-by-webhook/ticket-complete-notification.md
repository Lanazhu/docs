# Ticket Complete  Notification

### Ticket Notification Webhook

Webhooks are used to automatically receive notifications of events that happen.&#x20;

Once an event of "<mark style="color:green;">order.ticketed</mark>" is received on the server, it can be processed and action taken as required.

EndPoint ： The URL you configured to receive notifications&#x20;

Method : Post

{% tabs %}
{% tab title="Schema" %}
*   #### cid                                  <mark style="color:blue;">string</mark>                                                                                                &#x20;

    Identifier of client and user.
*   #### type                              <mark style="color:blue;">string</mark>                                                                                                 &#x20;

    Notification type.
* #### data                                                                                                                                                              <mark style="color:blue;"></mark>                                                                                      &#x20;
  *   #### orderNo                                  <mark style="color:blue;">string</mark>                                                                      &#x20;

      Order number.
  *   #### orderStatus                           <mark style="color:blue;">int</mark>                                                                            &#x20;

      orderStatus=2 means ticketed
  *   #### paxTicketInfos                     Array<[PAXTicketInfo](../shopping-and-ticketing/order.md#2.-paxticketinfo-schema)>                                   <mark style="color:blue;"></mark>                                  &#x20;

      Passengers' ticket information, the same format as the PAXTicketInfo in order response or retrive booking response, click [**here**](../shopping-and-ticketing/order.md#2.-paxticketinfo-schema) **** to check the schema
{% endtab %}

{% tab title="Samples" %}
```json
{
    "cid": "rggat40831",
    "type": "order.ticketed",
    "data":
    {
        "ticketNotification":
        {
            "orderNo": "BCNQL20201031184148568",
            "orderStatus": "2",
            "paxTicketInfos": [
            {
                "name": "EHRBAR/YANN",
                "passengerType": 0,
                "birthday": "19771029",
                "gender": "M",
                "cardNum": "G000000000",
                "cardType": "PP",
                "cardIssuePlace": "CH",
                "cardExpired": "20320118",
                "nationality": "CH",
                "ticketNos": [
                    "EDVLRZ"
                ],
                "airlinePNRs": [
                    "EDVLRZ"
                ],
                "ancillaries": []
            },
            {
                "name": "MOREL/JEROME",
                "passengerType": 0,
                "birthday": "19661118",
                "gender": "M",
                "cardNum": "G000000000",
                "cardType": "PP",
                "cardIssuePlace": "FR",
                "cardExpired": "20320118",
                "nationality": "FR",
                "ticketNos": [
                    "EDVLRZ"
                ],
                "airlinePNRs": [
                    "EDVLRZ"
                ],
                "ancillaries": []
            }
            ]
        }
    }  
}
```
{% endtab %}
{% endtabs %}
