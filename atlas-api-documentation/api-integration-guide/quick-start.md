---
description: This guide will walk you through how to go from nothing to your first booking!
---

# Quick Start

{% hint style="info" %}
This guide will walk you through how to go from nothing to your first booking!
{% endhint %}

Please follow the below steps to finish the integration with Atlas and expand your product suite.

![](<../../.gitbook/assets/Integration workflow (1) (1).jpg>)

## Get Atlas Sandbox Credential

The sandbox API credentials will be created and shared by your account manager.&#x20;

The API credentials contain two items : <mark style="color:green;">x-atlas-client-id</mark> and <mark style="color:green;">x-atlas-client-secret.</mark>

Your API requests are authenticated using API keys. Any request that doesn't include an API key will return an error.

Please add them in the header of each <mark style="color:blue;">post</mark> request.

{% hint style="success" %}
**Tip:** We've put together a Postman Collection that contains all of the requests you'll need to follow along with this guide, please download it here.
{% endhint %}

## Make your first request

EndPoint ：  [https://sandbox.atlaslovestravel.com/search.do](https://sandbox.atlaslovestravel.com/search.do)

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
    "tripType": "1",
    "adultNum": 1,
    "childNum": 0,
    "infantNum": 0,
    "fromCity": "JKT",
    "toCity": "DPS",
    "fromDate": "20220210",
    "retDate": ""
}
```


{% endtab %}

{% tab title="Response" %}
```json5
{
    "status": 0,
    "msg": "success",
    "routings": [
        {
            "routingIdentifier": "MOejxZ1eexlRUPzvRCF2hQJbVvnm+thHbXc8xQOl/Qtn8W03Dtrto/RqjhWZEqm32FSXQ/JNmWrQbXaA/wW4pAeQswWihhpjhcwAbrumGocZlX2xi51Q/gKig+9Z4zozwMtmnTcgflVgdy41eEAMIrx1vcmBE36sLlI1CzzoWb542yK/S3HNPtZ5m+fGVmx5Hr2UHIT/8rpfPmGVdMQmgkfy3eB/8G/PjNr3eMezb1T0ao4VmRKpt9hUl0PyTZlq0G12gP8FuKT4mPCCZpHI8Oyyuac+dWOndC/MAgRwN+vgU8UcZchBQsLdPPyWfaSx",
            "supportCreditTransPayment": "0",
            "currency": "USD",
            "adultPrice": 192.64,
            "adultTax": 13.10,
            "childPrice": 192.64,
            "childTax": 13.10,
            "InfantPrice": 0,
            "InfantTax": 0,
            "transactionFeePerPax": 5.00,
            "nationalityType": 0,
            "nationality": "",
            "suitAge": "",
            "PaxType": "ADT",
            "fromSegments": [
                {
                    "carrier": "JT",
                    "flightNumber": "JT791",
                    "depAirport": "AMQ",
                    "depTime": "202201240820",
                    "arrAirport": "UPG",
                    "arrTime": "202201240850",
                    "stopCities": "",
                    "duration": 90,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-800",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                },
                {
                    "carrier": "JT",
                    "flightNumber": "JT873",
                    "depAirport": "UPG",
                    "depTime": "202201241300",
                    "arrAirport": "CGK",
                    "arrTime": "202201241420",
                    "stopCities": "",
                    "duration": 140,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-800",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                }
            ],
            "retSegments": [],
            "combineIndexs": [],
            "rule": {
                "hasBaggage": 1,
                "baggageElements": [
                    {
                        "segmentNo": 1,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 1,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    }
                ],
                "refundRules": [
                    {
                        "refundType": 0,
                        "refundStatus": "T",
                        "refundFee": 0.0,
                        "currency": "CNY",
                        "refNoshow": "T",
                        "refNoShowCondition": 48,
                        "refNoshowFee": 0.0,
                        "ruleList": null
                    }
                ],
                "changesRules": [
                    {
                        "changesType": 0,
                        "changesStatus": "T",
                        "changesFee": 0.0,
                        "currency": "CNY",
                        "revNoshow": "T",
                        "revNoShowCondition": 48,
                        "revNoshowFee": 0.0,
                        "ruleList": []
                    }
                ]
            },
            "ancillaryProductElements": [
                {
                    "segmentIndex": 1,
                    "productCode": "SCI_BAG_JT_10KG_UJN7M7",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                },
                {
                    "segmentIndex": 2,
                    "productCode": "SCI_BAG_JT_10KG_NPOEFF",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                }
            ],
            "vendorFare": null
        },
        {
            "routingIdentifier": "MOejxZ1eexlRUPzvRCF2hQJbVvnm+thHbXc8xQOl/Qtn8W03Dtrto/RqjhWZEqm32FSXQ/JNmWrQbXaA/wW4pAeQswWihhpjhcwAbrumGocZlX2xi51Q/gKig+9Z4zozwMtmnTcgflVgdy41eEAMIrx1vcmBE36sLlI1CzzoWb542yK/S3HNPrkc1rMtOGmTHr2UHIT/8rrw3DHIR8FynUfy3eB/8G/PdDvijXmmNLz0ao4VmRKpt9hUl0PyTZlq0G12gP8FuKT4mPCCZpHI8Oyyuac+dWOndC/MAgRwN+vgU8UcZchBQsLdPPyWfaSx",
            "supportCreditTransPayment": "0",
            "currency": "USD",
            "adultPrice": 192.64,
            "adultTax": 13.10,
            "childPrice": 192.64,
            "childTax": 13.10,
            "InfantPrice": 0,
            "InfantTax": 0,
            "transactionFeePerPax": 5.00,
            "nationalityType": 0,
            "nationality": "",
            "suitAge": "",
            "PaxType": "ADT",
            "fromSegments": [
                {
                    "carrier": "JT",
                    "flightNumber": "JT791",
                    "depAirport": "AMQ",
                    "depTime": "202201240820",
                    "arrAirport": "UPG",
                    "arrTime": "202201240850",
                    "stopCities": "",
                    "duration": 90,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-800",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                },
                {
                    "carrier": "JT",
                    "flightNumber": "JT797",
                    "depAirport": "UPG",
                    "depTime": "202201241430",
                    "arrAirport": "CGK",
                    "arrTime": "202201241550",
                    "stopCities": "",
                    "duration": 140,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-900ER",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                }
            ],
            "retSegments": [],
            "combineIndexs": [],
            "rule": {
                "hasBaggage": 1,
                "baggageElements": [
                    {
                        "segmentNo": 1,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 1,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    }
                ],
                "refundRules": [
                    {
                        "refundType": 0,
                        "refundStatus": "T",
                        "refundFee": 0.0,
                        "currency": "CNY",
                        "refNoshow": "T",
                        "refNoShowCondition": 48,
                        "refNoshowFee": 0.0,
                        "ruleList": null
                    }
                ],
                "changesRules": [
                    {
                        "changesType": 0,
                        "changesStatus": "T",
                        "changesFee": 0.0,
                        "currency": "CNY",
                        "revNoshow": "T",
                        "revNoShowCondition": 48,
                        "revNoshowFee": 0.0,
                        "ruleList": []
                    }
                ]
            },
            "ancillaryProductElements": [
                {
                    "segmentIndex": 1,
                    "productCode": "SCI_BAG_JT_10KG_UJN7M7",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                },
                {
                    "segmentIndex": 2,
                    "productCode": "SCI_BAG_JT_10KG_NPOEFF",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                }
            ],
            "vendorFare": null
        }
    ]
}
```
{% endtab %}
{% endtabs %}



## Issue a Ticket

![](<../../.gitbook/assets/Issue ticket workflow (3).jpg>)

### 1. Search

EndPoint ：  [https://sandbox.atlaslovestravel.com/search.do](https://sandbox.atlaslovestravel.com/search.do)

Method : Post

Header:

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
Content-Type: application/json
Accept-Encoding: gzip
```

Click [here ](../api-reference/shopping-and-ticketing/search.md#request)to check the schema

{% tabs %}
{% tab title="Request" %}
```json
{
    "cid": "XXXXXXXX",
    "tripType": "1",
    "adultNum": 1,
    "childNum": 0,
    "infantNum": 0,
    "fromCity": "JKT",
    "toCity": "DPS",
    "fromDate": "20220210",
    "retDate": "",
    "baggagePiece": 0,
    "baggageWeight": 0
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "status": 0,
    "msg": "success",
    "routings": [
        {
            "routingIdentifier": "MOejxZ1eexlRUPzvRCF2hQJbVvnm+thHbXc8xQOl/Qtn8W03Dtrto/RqjhWZEqm32FSXQ/JNmWrQbXaA/wW4pAeQswWihhpjhcwAbrumGocZlX2xi51Q/gKig+9Z4zozwMtmnTcgflVgdy41eEAMIrx1vcmBE36sLlI1CzzoWb542yK/S3HNPtZ5m+fGVmx5Hr2UHIT/8rpfPmGVdMQmgkfy3eB/8G/PjNr3eMezb1T0ao4VmRKpt9hUl0PyTZlq0G12gP8FuKT4mPCCZpHI8Oyyuac+dWOndC/MAgRwN+vgU8UcZchBQsLdPPyWfaSx",
            "supportCreditTransPayment": "0",
            "currency": "USD",
            "adultPrice": 192.64,
            "adultTax": 13.10,
            "childPrice": 192.64,
            "childTax": 13.10,
            "InfantPrice": 0,
            "InfantTax": 0,
            "transactionFeePerPax": 5.00,
            "nationalityType": 0,
            "nationality": "",
            "suitAge": "",
            "PaxType": "ADT",
            "fromSegments": [
                {
                    "carrier": "JT",
                    "flightNumber": "JT791",
                    "depAirport": "AMQ",
                    "depTime": "202201240820",
                    "arrAirport": "UPG",
                    "arrTime": "202201240850",
                    "stopCities": "",
                    "duration": 90,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-800",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                },
                {
                    "carrier": "JT",
                    "flightNumber": "JT873",
                    "depAirport": "UPG",
                    "depTime": "202201241300",
                    "arrAirport": "CGK",
                    "arrTime": "202201241420",
                    "stopCities": "",
                    "duration": 140,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-800",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                }
            ],
            "retSegments": [],
            "combineIndexs": [],
            "rule": {
                "hasBaggage": 1,
                "baggageElements": [
                    {
                        "segmentNo": 1,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 1,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    }
                ],
                "refundRules": [
                    {
                        "refundType": 0,
                        "refundStatus": "T",
                        "refundFee": 0.0,
                        "currency": "CNY",
                        "refNoshow": "T",
                        "refNoShowCondition": 48,
                        "refNoshowFee": 0.0,
                        "ruleList": null
                    }
                ],
                "changesRules": [
                    {
                        "changesType": 0,
                        "changesStatus": "T",
                        "changesFee": 0.0,
                        "currency": "CNY",
                        "revNoshow": "T",
                        "revNoShowCondition": 48,
                        "revNoshowFee": 0.0,
                        "ruleList": []
                    }
                ]
            },
            "ancillaryProductElements": [
                {
                    "segmentIndex": 1,
                    "productCode": "SCI_BAG_JT_10KG_UJN7M7",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                },
                {
                    "segmentIndex": 2,
                    "productCode": "SCI_BAG_JT_10KG_NPOEFF",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                }
            ],
            "vendorFare": null
        },
        {
            "routingIdentifier": "MOejxZ1eexlRUPzvRCF2hQJbVvnm+thHbXc8xQOl/Qtn8W03Dtrto/RqjhWZEqm32FSXQ/JNmWrQbXaA/wW4pAeQswWihhpjhcwAbrumGocZlX2xi51Q/gKig+9Z4zozwMtmnTcgflVgdy41eEAMIrx1vcmBE36sLlI1CzzoWb542yK/S3HNPrkc1rMtOGmTHr2UHIT/8rrw3DHIR8FynUfy3eB/8G/PdDvijXmmNLz0ao4VmRKpt9hUl0PyTZlq0G12gP8FuKT4mPCCZpHI8Oyyuac+dWOndC/MAgRwN+vgU8UcZchBQsLdPPyWfaSx",
            "supportCreditTransPayment": "0",
            "currency": "USD",
            "adultPrice": 192.64,
            "adultTax": 13.10,
            "childPrice": 192.64,
            "childTax": 13.10,
            "InfantPrice": 0,
            "InfantTax": 0,
            "transactionFeePerPax": 5.00,
            "nationalityType": 0,
            "nationality": "",
            "suitAge": "",
            "PaxType": "ADT",
            "fromSegments": [
                {
                    "carrier": "JT",
                    "flightNumber": "JT791",
                    "depAirport": "AMQ",
                    "depTime": "202201240820",
                    "arrAirport": "UPG",
                    "arrTime": "202201240850",
                    "stopCities": "",
                    "duration": 90,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-800",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                },
                {
                    "carrier": "JT",
                    "flightNumber": "JT797",
                    "depAirport": "UPG",
                    "depTime": "202201241430",
                    "arrAirport": "CGK",
                    "arrTime": "202201241550",
                    "stopCities": "",
                    "duration": 140,
                    "codeShare": false,
                    "cabin": "",
                    "cabinClass": 1,
                    "seatCount": 4,
                    "aircraftCode": "737-900ER",
                    "depTerminal": "",
                    "arrTerminal": "",
                    "operatingCarrier": "",
                    "operatingFlightnumber": ""
                }
            ],
            "retSegments": [],
            "combineIndexs": [],
            "rule": {
                "hasBaggage": 1,
                "baggageElements": [
                    {
                        "segmentNo": 1,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 1,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 0,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    },
                    {
                        "segmentNo": 2,
                        "passengerType": 1,
                        "baggagePiece": 0,
                        "baggageWeight": 20
                    }
                ],
                "refundRules": [
                    {
                        "refundType": 0,
                        "refundStatus": "T",
                        "refundFee": 0.0,
                        "currency": "CNY",
                        "refNoshow": "T",
                        "refNoShowCondition": 48,
                        "refNoshowFee": 0.0,
                        "ruleList": null
                    }
                ],
                "changesRules": [
                    {
                        "changesType": 0,
                        "changesStatus": "T",
                        "changesFee": 0.0,
                        "currency": "CNY",
                        "revNoshow": "T",
                        "revNoShowCondition": 48,
                        "revNoshowFee": 0.0,
                        "ruleList": []
                    }
                ]
            },
            "ancillaryProductElements": [
                {
                    "segmentIndex": 1,
                    "productCode": "SCI_BAG_JT_10KG_UJN7M7",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                },
                {
                    "segmentIndex": 2,
                    "productCode": "SCI_BAG_JT_10KG_NPOEFF",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 74.81,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                }
            ],
            "vendorFare": null
        }
    ]
}
```
{% endtab %}
{% endtabs %}

Please record <mark style="color:green;">routingIdentifier</mark> of each routing offers.

### 2. Verify

Obtain the <mark style="color:green;">routingIdentifier</mark> of the selected routing, and send it in the verify request

EndPoint ：  [https://sandbox.atlaslovestravel.com/verify.do](https://sandbox.atlaslovestravel.com/verify.do)

Method : Post

Header:

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
Content-Type: application/json
Accept-Encoding: gzip
```

Click [here ](../api-reference/shopping-and-ticketing/verify.md#request)to check the schema

{% tabs %}
{% tab title="Request" %}
```json
{
    "cid": "XXXXXXXX",
    "routingIdentifier": "Nvm0BG9VCGJRUPzvRCF2hU1okLJgXsVU46VwnmDdMe/JgpxanH/Xja3hYaj9X/EHLiR7QMsFKwl97AMIwqGNDbcG9kV3bXzylDL2dNM3c07PTcQ67WyTJvK9ITR1HmHC2t2K1gUJztkSI4hVwhMjOGZUlo8qqzhJ8N3Bzta2M87ijqfQHCXkoLAseTdGienIy33IOIIHB6aknLdpZrvz8tCOBxWuNSYc0RRhtNsZ2n31GEmT5TthTQ\u003d\u003d"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "status":0,
    "msg":"success",
    "sessionId":"20e00a95-0eb1-44a4-b45c-ed358b12dc8a",
    "orderNo":"TBASP20220123212500763",
    "totalPrice":176.15,
    "totalTransactionFee":6.38,
    "currency":"CNY",
    "vendorTotalPrice":1411.24,
    "vendorCurrency":"PHP",
    "tktLimitTime":"2022-01-23 22:15:00",
    "pnrCode":"YO76ZF",
    "includeExtraBaggage":0,
    "paxTicketInfos":[
        {
            "name":"ZHAN/SAN LI",
            "passengerType":0,
            "birthday":"19731012",
            "gender":"M",
            "cardNum":"E00000000",
            "cardType":"PP",
            "cardIssuePlace":"HK",
            "cardExpired":"20240123",
            "nationality":"HK",
            "ticketNos":[

            ],
            "airlinePNRs":[

            ],
            "ancillaries":[

            ]
        }
    ],
    "routing":{
        "routingIdentifier":"fZLZw029cBVRUPzvRCF2hU1okLJgXsVUsFwV4I1Nrx0+IeBLujvH1Tviid634fozLt0sb7UwGvV/kRoSwhvTKJDn+QcARQ1JbBBBJK0aJ6FDZTnby0lKiPRJWJeAdVaqUxJV6TF0R3w4dtruLPIzETfWaFUbztP2R/Ld4H/wb88PYq34aqXFZDviid634fozLt0sb7UwGvV/kRoSwhvTKEDDCgG0Q21a16y8UbmfYUnBcsZk1oPoWGqjrFpf56gF",
        "supportCreditTransPayment":"0",
        "currency":"CNY",
        "adultPrice":103.14,
        "adultTax":73.01,
        "childPrice":103.14,
        "childTax":73.01,
        "InfantPrice":0,
        "InfantTax":0,
        "transactionFeePerPax":6.38,
        "nationalityType":0,
        "nationality":"",
        "suitAge":"",
        "PaxType":"ADT",
        "fromSegments":[
            {
                "carrier":"DG",
                "flightNumber":"DG6925",
                "depAirport":"CEB",
                "depTime":"202201251230",
                "arrAirport":"BXU",
                "arrTime":"202201251335",
                "stopCities":"",
                "duration":65,
                "codeShare":false,
                "cabin":"",
                "cabinClass":1,
                "seatCount":4,
                "aircraftCode":"AT7",
                "depTerminal":"",
                "arrTerminal":"",
                "operatingCarrier":"",
                "operatingFlightnumber":""
            }
        ],
        "retSegments":[

        ],
        "combineIndexs":[

        ],
        "rule":{
            "hasBaggage":0,
            "baggageElements":[
                {
                    "segmentNo":1,
                    "passengerType":0,
                    "baggagePiece":0,
                    "baggageWeight":0
                }
            ],
            "refundRules":[
                {
                    "refundType":0,
                    "refundStatus":"T",
                    "refundFee":0,
                    "currency":"CNY",
                    "refNoshow":"T",
                    "refNoShowCondition":48,
                    "refNoshowFee":0,
                    "ruleList":[

                    ]
                }
            ],
            "changesRules":[
                {
                    "changesType":0,
                    "changesStatus":"T",
                    "changesFee":0,
                    "currency":"CNY",
                    "revNoshow":"T",
                    "revNoShowCondition":48,
                    "revNoshowFee":0,
                    "ruleList":[

                    ]
                }
            ]
        },
        "ancillaryProductElements":[
            {
                "segmentIndex":1,
                "productCode":"BAG_DG_PH-PH_1_1P_20KG",
                "productName":"Baggage",
                "productType":1,
                "canPurchaseWithTicket":1,
                "canPurchasePostTicket":0,
                "price":59.51,
                "currency":"CNY",
                "auxBaggageElement":{
                    "piece":1,
                    "weight":20,
                    "isAllWeight":true
                }
            }
        ],
        "vendorFare":null
    }
}n
```
{% endtab %}
{% endtabs %}

From the verify response record the sessionid and the ancillaryProductElements which include all the ancillary offers.

### 3. Order

Obtain the <mark style="color:green;">sessionId</mark> of the verify response, and send it in the order request with passengers and contacts, as well as ancillary selections with <mark style="color:green;">productCode</mark> of each <mark style="color:green;">ancillaryProductElement</mark>

EndPoint ：  [https://sandbox.atlaslovestravel.com/order.do](https://sandbox.atlaslovestravel.com/order.do)

Method : Post

Header:

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
Content-Type: application/json
Accept-Encoding: gzip
```

Click [here ](../api-reference/shopping-and-ticketing/order.md#request)to check the schema

{% tabs %}
{% tab title="Request" %}
```json
{
    "cid": "XXXXXXXX",
    "sessionId": "ca6b0a58-74a4-40cd-90ac-3d097b7f3f5b",
    "passengers": [
        {
            "name": "SONG/YUN",
            "passengerType": 0,
            "birthday": "19900101",
            "gender": "M",
            "cardNum": "XXXXXXXX",
            "cardType": "PP",
            "cardIssuePlace": "SG",
            "cardExpired": "20300101",
            "nationality": "SG",
            "ancillaries": [
                {
                    "productCode": "SCI_BAG_5J_20KG_WULKSI",
                    "segmentIndex": 1
                }
            ]
        },
        {
            "name": "YAO/SAHA",
            "passengerType": 0,
            "birthday": "20120101",
            "gender": "M",
            "cardNum": "XXXXXXXX",
            "cardType": "PP",
            "cardIssuePlace": "SG",
            "cardExpired": "20300101",
            "nationality": "SG",
            "ancillaries": []
        }
    ],
    "contact": {
        "name": "Test",
        "address": null,
        "postcode": null,
        "email": "xxxxxx@yy.com",
        "mobile": "13000000000"
    },
    "passengerBaggages": null,
    "requestSource": ""
}
```


{% endtab %}

{% tab title="Response" %}
```json
{
    "status":0,
    "msg":"success",
    "sessionId":"20e00a95-0eb1-44a4-b45c-ed358b12dc8a",
    "orderNo":"TBASP20220123212500763",
    "totalPrice":176.15,
    "totalTransactionFee":6.38,
    "currency":"CNY",
    "vendorTotalPrice":1411.24,
    "vendorCurrency":"PHP",
    "tktLimitTime":"2022-01-23 22:15:00",
    "pnrCode":"YO76ZF",
    "includeExtraBaggage":0,
    "paxTicketInfos":[
        {
            "name":"ZHAN/SAN LI",
            "passengerType":0,
            "birthday":"19731012",
            "gender":"M",
            "cardNum":"E00000000",
            "cardType":"PP",
            "cardIssuePlace":"HK",
            "cardExpired":"20240123",
            "nationality":"HK",
            "ticketNos":[

            ],
            "airlinePNRs":[

            ],
            "ancillaries":[

            ]
        }
    ],
    "routing":{
        "routingIdentifier":"fZLZw029cBVRUPzvRCF2hU1okLJgXsVUsFwV4I1Nrx0+IeBLujvH1Tviid634fozLt0sb7UwGvV/kRoSwhvTKJDn+QcARQ1JbBBBJK0aJ6FDZTnby0lKiPRJWJeAdVaqUxJV6TF0R3w4dtruLPIzETfWaFUbztP2R/Ld4H/wb88PYq34aqXFZDviid634fozLt0sb7UwGvV/kRoSwhvTKEDDCgG0Q21a16y8UbmfYUnBcsZk1oPoWGqjrFpf56gF",
        "supportCreditTransPayment":"0",
        "currency":"CNY",
        "adultPrice":103.14,
        "adultTax":73.01,
        "childPrice":103.14,
        "childTax":73.01,
        "InfantPrice":0,
        "InfantTax":0,
        "transactionFeePerPax":6.38,
        "nationalityType":0,
        "nationality":"",
        "suitAge":"",
        "PaxType":"ADT",
        "fromSegments":[
            {
                "carrier":"DG",
                "flightNumber":"DG6925",
                "depAirport":"CEB",
                "depTime":"202201251230",
                "arrAirport":"BXU",
                "arrTime":"202201251335",
                "stopCities":"",
                "duration":65,
                "codeShare":false,
                "cabin":"",
                "cabinClass":1,
                "seatCount":4,
                "aircraftCode":"AT7",
                "depTerminal":"",
                "arrTerminal":"",
                "operatingCarrier":"",
                "operatingFlightnumber":""
            }
        ],
        "retSegments":[

        ],
        "combineIndexs":[

        ],
        "rule":{
            "hasBaggage":0,
            "baggageElements":[
                {
                    "segmentNo":1,
                    "passengerType":0,
                    "baggagePiece":0,
                    "baggageWeight":0
                }
            ],
            "refundRules":[
                {
                    "refundType":0,
                    "refundStatus":"T",
                    "refundFee":0,
                    "currency":"CNY",
                    "refNoshow":"T",
                    "refNoShowCondition":48,
                    "refNoshowFee":0,
                    "ruleList":[

                    ]
                }
            ],
            "changesRules":[
                {
                    "changesType":0,
                    "changesStatus":"T",
                    "changesFee":0,
                    "currency":"CNY",
                    "revNoshow":"T",
                    "revNoShowCondition":48,
                    "revNoshowFee":0,
                    "ruleList":[

                    ]
                }
            ]
        },
        "ancillaryProductElements":[
            {
                "segmentIndex":1,
                "productCode":"BAG_DG_PH-PH_1_1P_20KG",
                "productName":"Baggage",
                "productType":1,
                "canPurchaseWithTicket":1,
                "canPurchasePostTicket":0,
                "price":59.51,
                "currency":"CNY",
                "auxBaggageElement":{
                    "piece":1,
                    "weight":20,
                    "isAllWeight":true
                }
            }
        ],
        "vendorFare":null
    }
}jjson
```
{% endtab %}
{% endtabs %}

### 4. Pay

Record the <mark style="color:green;">orderNo</mark> from the order response and send it in the pay request.

EndPoint ：  [https://sandbox.atlaslovestravel.com/pay.do](https://sandbox.atlaslovestravel.com/pay.do)

Method : Post

Header:

```
x-atlas-client-id ： <Your clientid>
x-atlas-client-secret : <Your client secretid>
Content-Type: application/json
Accept-Encoding: gzip
```

Click [here ](../api-reference/shopping-and-ticketing/payment.md#request)to check the schema

{% tabs %}
{% tab title="Request" %}
```json
{
    "cid": "XXXXXXXXXX",
    "orderNo": "TBASP20220123212500763"
}
```


{% endtab %}

{% tab title="Response" %}
```json
{
    "status": 0,
    "msg": "success"
}
```
{% endtab %}
{% endtabs %}



### 5. Ticket Notification Webhook

Webhooks are used to automatically receive notifications of events that happen. For example; when an order has a schedule change the schedule change notification will be sent to the customer.

Please follow the steps [here ](../api-reference/notifications-by-webhook/register-webhook.md)to register your webhook and start receiving messages.

Once you receive an event of "<mark style="color:green;">order.ticketed</mark>" on your server, you can process and act on it as you need.

Click [here ](../api-reference/notifications-by-webhook/ticket-complete-notification.md)to check the schema, the sample is as follows.

{% tabs %}
{% tab title="Sample" %}
```json
{
    "cid": "XXXXXXXX",
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

