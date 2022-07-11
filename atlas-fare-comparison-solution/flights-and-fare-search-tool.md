# Flights & Fare Search Tool

## Overview

You can search and download flights and fare data. These rows of data can be compared with your own data at a time.

The workflow to achieve this is as below:

![](<../.gitbook/assets/image (25).png>)

{% hint style="info" %}
Atlas quotation consists of four parts as mentioned below :

* <mark style="color:blue;">Currency</mark>   &#x20;

&#x20;      Configured according to your demand during your application for fare comparison.

* <mark style="color:blue;">FarePrice</mark> &#x20;

&#x20;     The same as airline official price converted to your selected currency using the market FX rate.

* <mark style="color:blue;">Tax</mark>           &#x20;

&#x20;      The same as airline official tax converted to your selected currency using the market FX rate.

* <mark style="color:blue;">Booking Fee (Technical Service fee)</mark>  &#x20;

&#x20;      $0 in comparison results. For real transaction, the value will be set according to the contractual agreement between Atlas and your company
{% endhint %}

## 1-Submit Application for Comparison

The search tool application should be submitted to the Atlas account manager with 3 sets of information as mentioned below. The flights & fare search tool credentials will be created and shared by your account manager.&#x20;

1\) <mark style="color:blue;">Company name</mark>&#x20;

2\) <mark style="color:blue;">Email Address</mark>&#x20;

3\) <mark style="color:blue;">Fare Quote Currency</mark>

## 2-Get Atlas Flights & Fare Search Credential

You will get 3 sets of information below:

1\) URL of Flights & Fare Search Tool Portal&#x20;

2\) Private user id

3\) Default password



## 3-Use our search tool to download a batch of content for comparison

#### Search filters are bellow:

1\) One-way or Round-trip

2\) Departure Date

3\) Return Date

4\) Departure Country & Arrival Country

5\) Departure City & Arrival City

6\) Airline : IATA Airline Code

7\) Fare Quotation Currency : Configured according to your demand during your application for fare comparison.

#### Flights & fare content information are bellow:

If it is a round trip, you will get outbound and inbound flights and fare bellow.



| Column                        | Description                                                                                                                                  |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Flight No                     | If it is a transfer trip, the flight number of each segment is displayed one after another, and each flight number is separated by a comma   |
| Airline                       | If it is a connecting trip, the airline for each segment is displayed one after another, and each value is separated by a comma              |
| Dep Time                      | Format as yyyy/MM/dd HH:m                                                                                                                    |
| Arr Time                      | Format as yyyy/MM/dd HH:m                                                                                                                    |
| Stopover (Transfer) / Nonstop | Transfer / Nonstop                                                                                                                           |
| Total Flight Hours            | HHh MMm                                                                                                                                      |
| Dep Airport                   | 3 letter IATA airport code                                                                                                                   |
| Arr Airport                   | 3 letter IATA airport code                                                                                                                   |
| Dep City                      | 3 letter IATA city code                                                                                                                      |
| Arr City                      | 3 letter IATA city code                                                                                                                      |
| Cabin Class                   | Economy Class / Business Class / First Class                                                                                                 |
| Passenger Type                | <p>ADT: Ordinary adult price<br>STU: International student price<br>SEA: Seaman's price</p>                                                  |
| Fare Price                    | The net fare as provided by the airline                                                                                                      |
| Tax Fee                       | The total tax as provided by the airline                                                                                                     |
| Booking Fee                   | $0 in comparison results. For real transaction, the value will be set according to the contractual agreement between Atlas and your company. |
| Total Fare(Including TAX)     | Fare Price + Tax                                                                                                                             |
| Fare Quote Currency           | As per the settlement currency of your company                                                                                               |
| Fare Quote Time               | The time at which the fare quote response has been received from the Atlas Platform                                                          |

## Contact us

For applying flight & fare search tool, please contact your account manager.

For any questions or problems about using the search tool, please contact us on b2b\_product@atlaslovestravel.com

\


\
