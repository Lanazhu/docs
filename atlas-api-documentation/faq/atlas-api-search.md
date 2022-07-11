# Atlas API Search

#### Q. Can we get the fare results in user requested currency?

A. Currently we only give the results with the currency which we will settle with client. We don't offer the option to give fares with the requested currency. Please provide us with use cases where you would like to request a specific currency.

&#x20;

#### Q. Can we control/filter the carriers in search response?

A. We don't provide these options currently. This functionality is in our roadmap for Q12022.

&#x20;

#### Q. Why is there no tax break-up information in the search results?

A. Yes, we don't provide tax breakdown currently because a lot of LCCs don't provide this in their shopping response as well as in the PNR. It is our endeavor to provide tax breakdown in the future for airlines who provide this information.

&#x20;

#### Q. What does TransactionFeePerPax mean?

A. This is technical service fee which is not included in the airfare or tax. This fee is non-refundable.

&#x20;

#### Q. In the Segment Element schema a few critical nodes are missing like booking class, fare basis (to name a few)?

A. Contrary to GDSs, most of the LCCs do not provide cabin class and fare basis. Hence, these nodes are not mandatory in creating a PNR. In saying that, we have the information for the booking code. Please refer to the “cabin” element.

&#x20;

#### Q. How many records will be returned in the search response? What will be the sorting order?

A. By default we will return xx records in the search response. In the coming months we will provide an update through which the client can control the number of records being returned. The default sort order is from low fares to high fares.

&#x20;

#### Q. Does Atlas support special fares with passenger restrictions?

A. Special Fare with passenger restrictions like ages and nationalities are not supported currently, but we are planning to support them in Q2 2022.



#### Q. What is the tag “seatCount” denote in the search response?

A. This means "remaining seats for the fare". As a lot of LCCs have high reservation error rate when the passenger count is greater than 4, Atlas would limit the maximum seat count to 4.

Please avoid sending more than 4 passengers in the search request.

&#x20;

#### Q. What is the maximum time gap allowed between ‘search” and “revalidation”?

A. 2 hours. But when the time gap is longer, the price change possibility will be higher.

&#x20;

#### Q. What is the maximum time gap between revalidation and order?

A. 30 mins. But when the time gap is longer, the price change possibility will be higher.

&#x20;

#### Q. Can I use different passenger count in the order step other than search & revalidation steps?

A. Yes. If you use 1ADT for search and revalidation, you can still add passengers during order step.

But if you're using other options, it's better to keep the count the same during search, revalidation and order.
