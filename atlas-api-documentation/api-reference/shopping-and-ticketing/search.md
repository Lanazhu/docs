# Search

## Dependency

No preceding function needs to be carried out.

## Endpoint

[https://sandbox.atlaslovestravel.com/search.do](https://sandbox.atlaslovestravel.com/search.do)

## Request

{% tabs %}
{% tab title="Schema" %}
*   #### cid                 <mark style="color:blue;">string</mark>                                                                                                                  <mark style="color:green;">Required</mark>

    Identifier of client and user.
*   #### tripType      <mark style="color:blue;">string</mark>                                                                                                                  <mark style="color:green;">Required</mark>

    1: Oneway

    2: Return Trip
*   #### adultNum     <mark style="color:blue;">int</mark>                                                                                                                       <mark style="color:green;">Required</mark>

    Adult passenger count, the number can be 1-9
*   #### childNum      <mark style="color:blue;">int</mark>                                                                                                                       <mark style="color:green;">Required</mark>

    Adult passenger count, the number can be 0-8
*   #### infantNum    <mark style="color:blue;">int</mark>                                                                                                                       <mark style="color:orange;">Optional</mark>

    Reserved, currently not support infant purchase
*   #### fromCity      <mark style="color:blue;">string</mark>                                                                                                                 <mark style="color:green;">Required</mark>

    IATA City/Airport Code of departure city
*   #### toCity            <mark style="color:blue;">string</mark>                                                                                                                 <mark style="color:green;">Required</mark>

    IATA City/Airport Code of arrival city
*   #### fromDate     <mark style="color:blue;">string</mark>                                                                                                                 <mark style="color:green;">Required</mark>

    Departure date, the format is YYYYMMDD
*   #### retDate         <mark style="color:blue;">string</mark>                                                                                                                 <mark style="color:orange;">Optional</mark>

    Arrival date, the format is YYYYMMDD

    Must not be earlier than fromDate. And it can be blank if tripType=1.
*   #### requestSource         <mark style="color:blue;">string</mark>                                                                                                  <mark style="color:orange;">Optional</mark>

    Identify the source of the search traffic, E.g. Google Flights, Oganic Search, SkyScanner.
{% endtab %}

{% tab title="Samples" %}
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
    "requestSource": "Organic"
}
```
{% endtab %}
{% endtabs %}

## Response

{% tabs %}
{% tab title="Schema" %}
*   #### status     <mark style="color:blue;">int</mark>                                                                                                                         &#x20;

    0: success

    1: request data format error

    2: route is forbidden

    3: unauthorized access
*   #### msg         <mark style="color:blue;">string</mark>                                                                                                                   &#x20;

    Error message
*   #### routings   Array<[Routing Element](search.md#route-element-schema)>                                                                                               <mark style="color:blue;"></mark>                                                                                              &#x20;

    The array of the routings which include suitable flights and fares. click [<mark style="color:red;">here</mark> ](search.md#route-element-schema)to check the schema
{% endtab %}

{% tab title="Samples" %}
```json
{
    "status":0,
    "msg":"success",
    "routings":[
        {
            "routingIdentifier":"K7jWWc8Rq4ETSMWRHlhxhAMDhwUTz1Ty46VwnmDdMe8ZPZQyz3X0KkJxlQV1LwyENuuoYtO28B5k0QK+Vd8Ib4BmiiHQLzX9R7e0VPq8abH5gxFLgeOVQuerBxMqkOi239OWHU/iXVuggQcrbUJ3uxbMNdvNbRECTVvwV3xXgXl07i/72WQoPpN8EA8lik2pKNEtHMsuVpQDk6Wry7MaHQeNspRYJwDEY7i5tKVoTua5c8VEC8fd0g\u003d\u003d",
            "supportCreditTransPayment":"0",
            "currency":"USD",
            "adultPrice":16.46,
            "adultTax":10.98,
            "childPrice":16.46,
            "childTax":10.98,
            "InfantPrice":0,
            "InfantTax":0,
            "transactionFeePerPax":2,
            "nationalityType":0,
            "nationality":"",
            "suitAge":"",
            "PaxType":"ADT",
            "fromSegments":[
                {
                    "carrier":"IW",
                    "flightNumber":"IW1848",
                    "depAirport":"DPS",
                    "depTime":"202202041210",
                    "arrAirport":"LOP",
                    "arrTime":"202202041250",
                    "stopCities":"",
                    "duration":40,
                    "codeShare":false,
                    "cabin":"",
                    "cabinClass":1,
                    "seatCount":4,
                    "aircraftCode":"",
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
                        "refNoshowFee":0
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
                    "productCode":"BAG_IW_1_1P_10KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":18.61,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":10,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":1,
                    "productCode":"BAG_IW_1P_15KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":26.8,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":15,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":1,
                    "productCode":"BAG_IW_1_1P_20KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":37.22,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":20,
                        "isAllWeight":true
                    }
                }
            ],
            "vendorFare":null
        },
       {
            "routingIdentifier":"K7jWWc8Rq4ETSMWRHlhxhAMDhwUTz1Ty46VwnmDdMe8+9iUjY985ebmViBmzDc1XBptG/tw8XP3qStiFIM0TkNiO83lw4Go4PlwD34tTdxgo74G3LxIDLb0x2x/GJ+5lqHY8luoccEuvaHoJnXRdq96eRncqBt0fl8vDLAq5k/yfRcs6VgKolBGIC2Ud+VyoPlwD34tTdxhCT5N+M50KbYlJmLtdyVlrkNXMng1ISqaDhGqEzZGB0Xlhz1FL0gDU/9UivpvdJUtdvFy5jyNCOMeylCQHpGoJTbSm1kk+c6Q\u003d",
            "supportCreditTransPayment":"0",
            "currency":"USD",
            "adultPrice":31.56,
            "adultTax":21.04,
            "childPrice":31.56,
            "childTax":21.04,
            "InfantPrice":0,
            "InfantTax":0,
            "transactionFeePerPax":2,
            "nationalityType":0,
            "nationality":"",
            "suitAge":"",
            "PaxType":"ADT",
            "fromSegments":[
                {
                    "carrier":"JT",
                    "flightNumber":"JT919",
                    "depAirport":"DPS",
                    "depTime":"202202040835",
                    "arrAirport":"SUB",
                    "arrTime":"202202040830",
                    "stopCities":"",
                    "duration":55,
                    "codeShare":false,
                    "cabin":"",
                    "cabinClass":1,
                    "seatCount":4,
                    "aircraftCode":"",
                    "depTerminal":"",
                    "arrTerminal":"",
                    "operatingCarrier":"",
                    "operatingFlightnumber":""
                },
                {
                    "carrier":"JT",
                    "flightNumber":"JT822",
                    "depAirport":"SUB",
                    "depTime":"202202040930",
                    "arrAirport":"LOP",
                    "arrTime":"202202041135",
                    "stopCities":"",
                    "duration":65,
                    "codeShare":false,
                    "cabin":"",
                    "cabinClass":1,
                    "seatCount":4,
                    "aircraftCode":"",
                    "depTerminal":"",
                    "arrTerminal":"",
                    "operatingCarrier":"",
                    "operatingFlightnumber":""
                }
            ],
            "retSegments":[

            ],
            "rule":{
                "hasBaggage":1,
                "baggageElements":[
                    {
                        "segmentNo":1,
                        "passengerType":0,
                        "baggagePiece":0,
                        "baggageWeight":20
                    },
                    {
                        "segmentNo":2,
                        "passengerType":0,
                        "baggagePiece":0,
                        "baggageWeight":20
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
                        "refNoshowFee":0
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
                    "productCode":"BAG_JT_DPS-SUB_1,2,3_1P_10KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":12.27,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":10,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":1,
                    "productCode":"BAG_JT_DPS-SUB_1,2,3_1P_15KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":17.91,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":15,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":1,
                    "productCode":"BAG_JT_DPS-SUB_1,2,3_1P_20KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":23.55,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":20,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":1,
                    "productCode":"BAG_JT_DPS-SUB_1,2,3_1P_30KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":34.83,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":30,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":2,
                    "productCode":"BAG_JT_SUB-LOP_1,2,3_1P_10KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":14.39,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":10,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":2,
                    "productCode":"BAG_JT_SUB-LOP_1,2,3_1P_15KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":21.09,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":15,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":2,
                    "productCode":"BAG_JT_SUB-LOP_1,2,3_1P_20KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":27.78,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":20,
                        "isAllWeight":true
                    }
                },
                {
                    "segmentIndex":2,
                    "productCode":"BAG_JT_SUB-LOP_1,2,3_1P_30KG",
                    "productName":"Baggage",
                    "productType":1,
                    "price":41.17,
                    "currency":"USD",
                    "auxBaggageElement":{
                        "piece":1,
                        "weight":30,
                        "isAllWeight":true
                    }
                }
            ],
            "vendorFare":null
        }
   ]
}s
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
The search results will include a lot of items. Some hightlight points are as belows : &#x20;

* The returned <mark style="color:blue;">currency</mark> is by configuration according to the business agreement between you and Atlas
* The total cost to purchase this routing for a single <mark style="color:blue;"></mark> adult passenger is as follows:

&#x20;     <mark style="color:blue;">adultPrice</mark> + <mark style="color:blue;">adultTax</mark> + <mark style="color:blue;">transactionFeePerPax</mark>

*   For the airlines which support pass through payment method, we would set <mark style="color:blue;">supportCreditTransPayment</mark> to 1 and present the vendor's fare in the <mark style="color:blue;">vendorFare</mark> Element.&#x20;

    In reverse, if the airline doesn't support pass through payment method, we would set supportCreditTransPayment to 0 and the vendorFare Element will be null.
* <mark style="color:blue;">ancillaryProductElements</mark> in search response can be shown or hidden according to the configuration of each client in the backend system.
{% endhint %}

### <mark style="color:blue;">Route Element Schema</mark>

{% tabs %}
{% tab title="Schema" %}
*   #### routingIdentifier     <mark style="color:blue;">string</mark>                                                                                                    &#x20;

    The unique identifier for a particular route It will be used in the verify request.
*   #### supportCreditTransPayment   <mark style="color:blue;">string</mark>

    The tag to identify if the fare support the client to pay with client's credit card.

    1    represents    support credit card transpayment

    0   represents     Not support credit card transpayment
*   #### currency    <mark style="color:blue;">string</mark>

    Currency.
*   #### adultPrice   <mark style="color:blue;">decimal</mark>

    Adult fare per passenger.
*   #### adultTax      <mark style="color:blue;">decimal</mark>

    Adult tax per passenger.
*   #### childPrice   <mark style="color:blue;">decimal</mark>

    Child fare per passenger.
*   #### childTax      <mark style="color:blue;">decimal</mark>

    Child tax per passenger.
*   #### InfantPrice   <mark style="color:blue;">decimal</mark>

    Reserved, currently not support infant purchase.
*   #### InfantTax      <mark style="color:blue;">decimal</mark>

    Reserved, currently not support infant purchase.
*   #### transactionFeePerPax    <mark style="color:blue;">decimal</mark>

    Technical service fee per passenger.
*   #### nationalityType     <mark style="color:blue;">int</mark>

    Nationality limitation type

    0 No Limitation

    1 Allowed

    2 Forbidden
*   #### nationality     <mark style="color:blue;">string</mark>

    Nationality limitation value

    IATA country code, use comma if more than one country

    Blank means no limitation.
*   #### suitAge        <mark style="color:blue;">string</mark>

    Passenger age limitation

    The format is 12-24

    Blank means no limitation.
*   #### paxType      <mark style="color:blue;">string</mark>

    Currently only ADT fare is available.
*   #### fromSegments      Array<[Segment Element](search.md#3.-segment-element-schema)>

    Outbound segments, click [<mark style="color:red;">**here**</mark> ](search.md#segment-element-schema)to check the schema
*   #### retSegments         Array<[Segment Element](search.md#3.-segment-element-schema)>

    Inbound segments, click [<mark style="color:red;">**here**</mark> ](search.md#segment-element-schema)to check the schema
*   #### rule                Object<[RuleElement](search.md#5.-rule-element-schema)>

    RuleElement, click [<mark style="color:red;">**here**</mark>](search.md#rule-element-schema) <mark style="color:red;">****</mark> to check the schema
*   #### ancillaryProductElements    Array<[AncillaryProductElement](search.md#9.-ancillaryproduct-element-schema)>

    Currently only baggage is available in ancillaries.

    * #### [AncillaryProductElement](search.md#9.-ancillaryproduct-element-schema)
      *   #### segmentIndex                              <mark style="color:blue;">int</mark>

          Segment sequence, start from 1

          If it is return trip, sequence outbond and inbound together
      *   #### productCode                                <mark style="color:blue;">string</mark>

          Unique identifier for the ancillary product

          It would be used in the order request
      *   #### productName                                <mark style="color:blue;">string</mark>

          Ancillary product name
      *   #### productType                                 <mark style="color:blue;">int</mark>

          Ancillary product type

          1: baggage

          Currently only baggage is available
      *   #### price                                                 <mark style="color:blue;">decimal</mark>

          Price for this ancillary
      *   #### currency                                          <mark style="color:blue;">string</mark>

          Currency for this price
      * #### auxBaggageElement                 Object<[AuxBaggageElement](search.md#10.-auxbaggage-element-schema)>
        * #### [AuxBaggageElement](search.md#10.-auxbaggage-element-schema)
          *   #### piece                                                 <mark style="color:blue;">int</mark>

              0：No Limitation about piece;

              \>0：Maximum pieces
          *   #### weight                                             <mark style="color:blue;">int</mark>

              Maximum weight for ancillary baggage;

              Should be greater than 0
          *   #### isAllWeight                                   <mark style="color:blue;">boolean</mark>

              True：The weight is for all the pieces;

              False：The weight is for each piece
*   #### vendorFare     Object<[VendorFare Element](search.md#4.-vendorfare-element-schema)>

    To identify the vendor’s fare with vendor’s currency. It is only availabe when supportCreditTransPayment = 1
* #### [VendorFare Element](search.md#4.-vendorfare-element-schema)
  *   #### vendorAdultPrice         <mark style="color:blue;">decimal</mark>

      Adult fare per passenger in vendor’s currency.
  *   #### vendorAdultTax             <mark style="color:blue;">decimal</mark>

      Adult tax per passenger in vendor’s currency.
  *   #### vendorChildPrice          <mark style="color:blue;">decimal</mark>

      Child fare per passenger in vendor’s currency.
  *   #### vendorChildTax              <mark style="color:blue;">decimal</mark>

      Child tax per passenger in vendor’s currency.
  *   #### vendorCurrency             <mark style="color:blue;">string</mark>

      Vendor’s currency.
{% endtab %}
{% endtabs %}

### <mark style="color:blue;">Segment Element Schema</mark>

{% tabs %}
{% tab title="Schema" %}
*   #### carrier                       <mark style="color:blue;">string</mark>                                                                                                    &#x20;

    IATA code of airline.
*   #### flightNumber         <mark style="color:blue;">string</mark>

    Flight number

    The format is : CA123 or TR021 or FR1290.
*   #### depAirport              <mark style="color:blue;">string</mark>

    IATA code of departure airport.
*   #### depTime                  <mark style="color:blue;">string</mark>

    Departure time of the flight

    The format is ：yyyyMMddHHmm, 202203100300 means 10MAR2022 03:00
*   #### arrAirport                <mark style="color:blue;">string</mark>

    IATA code of arrival airport
*   #### arrTime                     <mark style="color:blue;">string</mark>

    Arrival time of the flight

    The format is ：yyyyMMddHHmm, 202203100300 means 10MAR2022 03:00
*   #### stopCities               <mark style="color:blue;">string</mark>

    Stop airports of the fight, IATA code, , use "," to separate if transfer airports count is higher than 1. E.g. "CGK,SUB".

    Blank means non-stop flight.
*   #### duration               <mark style="color:blue;">int</mark>

    The flying time of this flight with the unit in minutes.
*   #### codeShare              <mark style="color:blue;">boolean</mark>

    True : code share

    False : Not code share
*   #### cabin                         <mark style="color:blue;">string</mark>

    Booking code for the fare.

    In terms of the LCCs which do not provide this, the cabin would be blank
*   #### cabinClass             <mark style="color:blue;">int</mark>

    Service grade of the fare

    1 : Economy

    2 : Business

    3 : First Class
*   #### seatCount              <mark style="color:blue;">int</mark>

    Remaining seats for the fare.
*   #### aircraftCode           <mark style="color:blue;">string</mark>

    Aircraft equipment
*   #### depTerminal            <mark style="color:blue;">string</mark>

    Departure terminal
*   #### arrTerminal               <mark style="color:blue;">string</mark>

    Arrival terminalal
*   #### operatingCarrier     <mark style="color:blue;">string</mark>

    Operating carrier

    It is blank when codeShare=false
*   #### operatingFlightnumber      <mark style="color:blue;">string</mark>

    Operating flight number

    It is blank when codeShare=false
{% endtab %}
{% endtabs %}

### <mark style="color:blue;">Rule Element Schema</mark>

{% tabs %}
{% tab title="Schema" %}
*   #### hasBaggage                              <mark style="color:blue;">int</mark>

    A tag to identify if the fare include free checked-in baggage

    0 : Not included

    1 : Included
*   #### BaggageElements                 Array<[BaggageElement](search.md#6.-baggage-element-schema)>

    Free checked-in baggage information included in the fare.

    * #### [BaggageElement](search.md#6.-baggage-element-schema)
      *   #### segmentNo                              <mark style="color:blue;">int</mark>

          Segment sequence, start from 1.

          If it is roundtrip, sequence outbond and inbound together.
      *   #### passengerType                     <mark style="color:blue;">string</mark>

          0: ADT

          1: CHD

          2: INF

          If search or verify for ADT only, then only ADT is returned;

          If search or verify for ADT+CHD, then ADT and CHD are returned.
      *   #### baggagePiece                        <mark style="color:blue;">int</mark>

          Baggage pieces：

          0  No limitation

          \>0 Maximum pieces
      *   #### baggageWeight                    <mark style="color:blue;">int</mark>

          Baggage Weight, with the unit of KG

          0  means No Free baggage
*   #### refundRules                              Array<[RefundElement](search.md#7.-refund-element-schema)>

    Refund rules.

    * #### [RefundElement](search.md#7.-refund-element-schema)
      *   #### refundType                               <mark style="color:blue;">int</mark>

          Refund Type

          0：Wholly unused ticket;

          1：Partially used ticket(For example when the passenger has used outbound flight, and want to refund inbound flight)
      *   #### refundStatus                           <mark style="color:blue;">string</mark>

          Refund rule type

          T：Non refundable;

          H：Refundable with restrictions;

          F：Free for refund
      *   #### refundFee                                 <mark style="color:blue;">decial</mark>

          Refund fee

          If refundStatus =H, it should not be null;

          If refundStatus =T/F, it can be null.
      *   #### currency                                    <mark style="color:blue;">string</mark>

          Currency of refund fee

          If refundStatus =H, it should not be null.
      *   #### refNoshow                                <mark style="color:blue;">string</mark>

          Refund status when noshow happens

          T：Non refundable;

          H：Refundable with restrictions;

          F：Free for refund
      *   #### refNoShowCondition           <mark style="color:blue;">string</mark>

          How many hours before departure means no show
      *   #### refNoshowFee                         <mark style="color:blue;">string</mark>

          Total refund fee when noshow happens

          If refNoshow =H，it should not be null;

          This value includes the refund fee and noshow penalty when noshow happens
*   #### changesRules                         Array<[ChangesElement](search.md#8.-change-element-schema)>

    Change rules

    * #### [ChangesElement](search.md#8.-change-element-schema)
      *   #### changesType                              <mark style="color:blue;">int</mark>

          Change flight type

          0：Wholly unused ticket;

          1：Partially used ticket(For example when the passenger has used outbound flight, and want to refund inbound flight)
      *   #### changesStatus                          <mark style="color:blue;">string</mark>

          Change flight rule type

          T：Non changeable;

          H：Changeable with restrictions;

          F：Free for change flight
      *   #### changesFee                                 <mark style="color:blue;">decial</mark>

          Change flight fee

          If changesStatus =H, it should not be null;

          If changesStatus =T/F, it can be null.
      *   #### currency                                       <mark style="color:blue;">string</mark>

          Currency of change fee

          If changesStatus =H, it should not be null.
      *   #### refNoshow                                   <mark style="color:blue;">string</mark>

          Change flight rule when noshow happens

          T：Non changeable;

          H：Changeable with restrictions;

          F： Free for change flight
      *   #### refNoShowCondition               <mark style="color:blue;">int</mark>

          How many hours before departure means no show
      *   #### refNoshowFee                            <mark style="color:blue;">string</mark>

          Total fee for change flight when noshow happens

          If refNoshow =H，it should not be null;

          This value includes the change flight fee and noshow penalty when noshow happens
{% endtab %}
{% endtabs %}

## How to ...... <a href="#owrt" id="owrt"></a>

### 1. How to search for Oneway or Roundtrip flights? <a href="#owrt" id="owrt"></a>

If you want to search for oneway flights, please set tripType as 1 and keep retDate blank

```json
{
    "tripType": "1",
    "fromDate": "20220125",
    "retDate": "",
}
```

In the response, the retSegments of each routing will be empty

```json
"routings": [
    {
        "fromSegments": [
            {...}
        ],
        "retSegments": []
    },
    {
        "fromSegments": [
            {...}
        ],
        "retSegments": []
    },
    ...
]
```

If you want to search for roundtrip flights, please set tripType as 2 and input retDate

```css
{
    "tripType": "2",
    "fromDate": "20220125",
    "retDate": "20220128",
}
```

In the response, the <mark style="color:green;">retSegments</mark> of each routing will have data.

```json
"routings": [
    {
        "fromSegments": [
            {...}
        ],
        "retSegments": [
            {...}
        ]
    },
    {
        "fromSegments": [
            {...}
        ],
        "retSegments": [
            {...}
        ]
    },
    ...
]
```

### 2.How to identify direct or connection flights

Regarding direct flights, there will be only one segment in fromSegments or retSegments

```javascript
 {
 "fromSegments": [
                {
                    ...
                }
            ],
 "retSegments": [
                {
                    ...
                }
            ]
}
```

Regarding connection flights, there will be multiple segments in fromSegments or retSegments

```json
 {
 "fromSegments": [
                {
                    ...
                },
                {
                    ...
                }
            ],
 "retSegments": [
                {
                    ...
                },
                {
                    ...
                },
                {
                    ...
                }
            ]
}
```

### 3.Where is the baggage allowance mentioned?

#### 1) Free checked-in baggage

The free checked-in baggage allowance of each fare is available within both “search” and the “verify” response.

{% tabs %}
{% tab title="Schema" %}
#### Baggage Element

*   #### segmentNo                              <mark style="color:blue;">int</mark>

    Segment sequence, start from 1.

    If it is roundtrip, sequence outbond and inbound together.
*   #### passengerType                     <mark style="color:blue;">string</mark>

    0: ADT

    1: CHD

    2: INF

    If search or verify for ADT only, then only ADT is returned;

    If search or verify for ADT+CHD, then ADT and CHD are returned.
*   #### baggagePiece                        <mark style="color:blue;">int</mark>

    Baggage pieces：

    0  No limitation

    \>0 Maximum pieces
*   #### baggageWeight                    <mark style="color:blue;">int</mark>

    Baggage Weight, with the unit of KG

    0  means No Free baggage
{% endtab %}

{% tab title="Samples" %}
```json
{
...,
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
                "refundRules": [{...}],
                "changesRules":[{...}]
            }
...
}jso
```
{% endtab %}
{% endtabs %}

#### 2) Extra baggage offering

The details of the extra baggage offering are available in the ancillaryProductElements within both “search” and the “verify” response

{% tabs %}
{% tab title="Schema" %}
#### ancillaryProductElement

*   #### segmentIndex                              <mark style="color:blue;">int</mark>

    Segment sequence, start from 1

    If it is return trip, sequence outbond and inbound together
*   #### productCode                                <mark style="color:blue;">string</mark>

    Unique identifier for the ancillary product

    It would be used in the order request
*   #### productName                                <mark style="color:blue;">string</mark>

    Ancillary product name
*   #### productType                                 <mark style="color:blue;">int</mark>

    Ancillary product type

    1: baggage

    Currently only baggage is available
*   #### price                                                 <mark style="color:blue;">decimal</mark>

    Price for this ancillary
*   #### currency                                          <mark style="color:blue;">string</mark>

    Currency for this price
* #### auxBaggageElement                 Object<<mark style="color:blue;">AuxBaggageElement</mark>>
  * #### AuxBaggageElement
    *   #### piece                                                 <mark style="color:blue;">int</mark>

        0：No Limitation about piece;

        \>0：Maximum pieces
    *   #### weight                                             <mark style="color:blue;">int</mark>

        Maximum weight for ancillary baggage;

        Should be greater than 0
    *   #### isAllWeight                                   <mark style="color:blue;">boolean</mark>

        True：The weight is for all the pieces;

        False：The weight is for each piece
{% endtab %}

{% tab title="Samples" %}
```json
 "ancillaryProductElements": [
                {
                    "segmentIndex": 1,
                    "productCode": "SCI_BAG_5J_5KG_WULKSI",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 1.02,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 5,
                        "isAllWeight": true
                    },
                    "offerId": null
                },
                {
                    "segmentIndex": 1,
                    "productCode": "SCI_BAG_5J_20KG_WULKSI",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 4.06,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 20,
                        "isAllWeight": true
                    },
                    "offerId": null
                },
                {
                    "segmentIndex": 2,
                    "productCode": "SCI_BAG_5J_10KG_WULKSI",
                    "productName": "StandardCheckInBaggage",
                    "productType": 1,
                    "canPurchaseWithTicket": 1,
                    "canPurchasePostTicket": 1,
                    "price": 2.03,
                    "currency": "USD",
                    "auxBaggageElement": {
                        "piece": 0,
                        "weight": 10,
                        "isAllWeight": true
                    },
                    "offerId": null
                }
            ]
```
{% endtab %}
{% endtabs %}

