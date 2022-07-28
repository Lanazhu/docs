# Errors

Atlas uses standard [HTTP response codes](https://httpstatuses.com/) to indicate the success or failure of API requests.

### Status codes

| Code                                | Reason                    | Description                                                                                                                                                                      |
| ----------------------------------- | ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [200](https://httpstatuses.com/200) | **OK**                    | The request was successful                                                                                                                                                       |
| [201](https://httpstatuses.com/201) | **Created**               | The request was successful, and a new resource was created                                                                                                                       |
| [204](https://httpstatuses.com/204) | **No Content**            | The request was successful, but there is no response to send back                                                                                                                |
| [400](https://httpstatuses.com/400) | **Bad Request**           | The request was invalid, for example due to missing headers                                                                                                                      |
| [401](https://httpstatuses.com/401) | **Unauthorized**          | An access token wasn't provided, or the provided token was invalid                                                                                                               |
| [403](https://httpstatuses.com/403) | **Forbidden**             | A valid access token was provided, but it didn't have sufficient permissions                                                                                                     |
| [404](https://httpstatuses.com/404) | **Not Found**             | The requested resource doesn't exist                                                                                                                                             |
| [406](https://httpstatuses.com/406) | **Not Acceptable**        | The response type you requested with your `Accept` header isn't supported                                                                                                        |
| [422](https://httpstatuses.com/422) | **Unprocessable Entity**  | A validation error occurred                                                                                                                                                      |
| [429](https://httpstatuses.com/429) | **Too Many Requests**     | You made too many requests to the API in a short period of time                                                                                                                  |
| [500](https://httpstatuses.com/500) | **Internal Server Error** | Something went wrong on our side. Contact support or try again later.                                                                                                            |
| [502](https://httpstatuses.com/502) | **Bad Gateway**           | The server, while acting as a gateway or proxy, received an invalid response from an inbound server it accessed while attempting to fulfill the request.                         |
| [503](https://httpstatuses.com/503) | **Service Unavailable**   | The server is currently unable to handle the request due to a temporary overload or scheduled maintenance, which will likely be alleviated after some delay. Try again later.    |
| [504](https://httpstatuses.com/504) | **Gateway Timeout**       | The server, while acting as a gateway or proxy, did not receive a timely response from an upstream server it needed to access in order to complete the request. Try again later. |



### **Error codes**

An error's `code` is an enum of the following values:

| Value   | Description                     |
| ------- | ------------------------------- |
| **`1`** | Data check error                |
| **`2`** | System error                    |
| **`3`** | Unauthorized access             |
| **`4`** | Empty data error                |
| **`5`** | Data encrytion verify error     |
| **6**   | Fare change error while booking |



### Ticket error codes

| Code                                 | Description                     |
| ------------------------------------ | ------------------------------- |
| <mark style="color:blue;">601</mark> | Price changes                   |
| <mark style="color:blue;">602</mark> | Flight not found                |
| <mark style="color:blue;">603</mark> | Position is full                |
| <mark style="color:blue;">604</mark> | Pay for failure                 |
| <mark style="color:blue;">605</mark> | Wrong passenger information     |
| <mark style="color:blue;">606</mark> | Inconsistent flight information |
| <mark style="color:blue;">607</mark> | FareFamily is sold out          |



