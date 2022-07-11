# Get Schedule Change Notification

### Schedule Change Notification Webhook

Webhooks are used to automatically receive notifications of events that happen.&#x20;

Once you receive an event of "<mark style="color:green;">order.schedulechange</mark>" on your server, it can be processed and relevant action taken.

EndPoint ： The URL you configured to receive notifications&#x20;

Method : Post

{% tabs %}
{% tab title="Samples" %}
```json
{
    "cid":"XXXXXXXX",
    "type":"order.schedulechange",
    "data":{
            "previousSeg":[
                {
                    "carrier":"PC",
                    "flightNumber":"PC2673",
                    "depAirport":"ESB",
                    "depTime":"2020-02-08 20:45:00",
                    "arrAirport":"SAW",
                    "arrTime":"2020-02-08 22:50:00",
                    "departureTerminal":"",
                    "arrivingTerminal":""
                },
                {
                    "carrier":"PC",
                    "flightNumber":"PC2674",
                    "depAirport":"SAW",
                    "depTime":"2020-02-08 23:55:00",
                    "arrAirport":"ASR",
                    "arrTime":"2020-02-09 01:20:00",
                    "departureTerminal":"",
                    "arrivingTerminal":""
                }
            ],
            "revisedSeg":[
                {
                    "carrier":"PC",
                    "flightNumber":"PC2673",
                    "depAirport":"ESB",
                    "depTime":"2020-02-08 21:45:00",
                    "arrAirport":"SAW",
                    "arrTime":"2020-02-08 23:50:00",
                    "departureTerminal":"",
                    "arrivingTerminal":""
                },
                {
                    "carrier":"PC",
                    "flightNumber":"PC2800",
                    "depAirport":"SAW",
                    "depTime":"2020-02-09 01:50:00",
                    "arrAirport":"ASR",
                    "arrTime":"2020-02-09 03:55:00",
                    "departureTerminal":"",
                    "arrivingTerminal":""
                }
            ],
            "scheduleChangeType":1
    }
}
```
{% endtab %}
{% endtabs %}
