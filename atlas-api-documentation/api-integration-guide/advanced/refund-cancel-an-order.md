# Refund/Cancel an Order

## WorkFlow

![](<../../../.gitbook/assets/Refund Process (3).jpg>)

## Description

### 1.Refund Quotation

Send the orderNo, together with the combination of passenger name and segment information(including depAirport, arrAirport, depDate and flightNo)

EndPoint ：  [https://sandbox.atlaslovestravel.com/refundQuotation.do](https://sandbox.atlaslovestravel.com/refundQuotation.do)

Method : Post

Header:

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
Content-Type: application/json
Accept-Encoding: gzip
```

{% tabs %}
{% tab title="Request" %}
```json
{
    "cid":"XXXXXXXX",
    "orderNo":"XPFIW20220209163159425",
    "refundRequestList":[
        {
            "lastName":"TEST",
            "firstName":"ONE",
            "segments":[
                {
                    "depDate":"20220302",
                    "flightNo":"5J562",
                    "depAirport":"CEB",
                    "arrAirport":"MNL"
                }
            ]
        },
        {
            "lastName":"TEST",
            "firstName":"THREE",
            "segments":[
                {
                    "depDate":"20220302",
                    "flightNo":"5J562",
                    "depAirport":"CEB",
                    "arrAirport":"MNL"
                }
            ]
        }
    ]
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "status": 0,
    "msg": "success",
    "isRefundable": true,
    "currency": "USD",
    "originalTotalFareAmount": 37.14,
    "originalTotalAncillaryAmount": 8.12,
    "originalTotalAmount": 45.26,
    "airlinePenaltyAmountForFare": 0.00,
    "airlinePenaltyAmountForAncillaries": 0.00,
    "airlinePenaltyAmount": 0.00,
    "estimatedRefundAmount": 45.26,
    "transactionFee": 2.00,
    "refundOfferId": "7961ab5b202642628e9595498ffea083"   
}
```
{% endtab %}
{% endtabs %}

### 2.Refund

If you confirm the fare quote of the refund, Send the same request schema to the refund endpoint to submit the confirmation.

EndPoint ：  [https://sandbox.atlaslovestravel.com/refund.do](https://sandbox.atlaslovestravel.com/refund.do)

Method : Post

Header:

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
Content-Type: application/json
Accept-Encoding: gzip
```

{% tabs %}
{% tab title="Request" %}
```json
{
    "cid": "XXXXXXXX",
    "orderNo": "XPFIW20220209163159425",
    "refundOfferId":"xxxxxxxxxxxxxxxxxxxxx"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "status": 0,
    "msg": "success"
    "refundStatus": 0,
    "currency": "USD",
    "originalTotalFareAmount": 37.14,
    "originalTotalAncillaryAmount": 8.12,
    "originalTotalAmount": 45.26,
    "airlinePenaltyAmountForFare": 0.00,
    "airlinePenaltyAmountForAncillaries": 0.00,
    "airlinePenaltyAmount": 0.00,
    "estimatedRefundAmount": 45.26,
    "transactionFee": 2.00,
    "refundOfferId": "7961ab5b202642628e9595498ffea083",
    "isRefundable": true   
}
```
{% endtab %}
{% endtabs %}

### 3.Refund Status Notification

Webhooks are used to automatically receive notifications of events that happen.&#x20;

Once an event of "<mark style="color:green;">order.refundCompleted</mark>" is received on the server, it can be processed and action taken as required.

EndPoint ： The URL you configured to receive notifications&#x20;

Method : Post

{% tabs %}
{% tab title="Samples" %}
```json
{
    "cid":"XXXXXXXX",
    "type":"order.refundComplete",
    "data":{
         "orderNo":"PSTEV20220119165629057",
         "refundStatus":"2",
         "currency": "USD",
         "originalTotalFare": 37.32,
         "originalTotalAncillaryAmount": 10,
         "originalTotalAmount": 47.32,
         "airlinePenaltyAmountForFare": 5,
         "airlinePenaltyAmountForAncillaries": 0,
         "airlinePenaltyAmount":0,
         "finalRefundAmount":37.32,
         "transactionFee": 2
    }
}    
```
{% endtab %}
{% endtabs %}

