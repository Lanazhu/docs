# Test mode

## Test mode <a href="#overview" id="overview"></a>

The integration to Atlas needs to be built in the TEST mode.

Test mode is a "sandbox" which lets you use the Atlas API risk-free, with no danger of spending any money or booking flights you don't want!

You'll need to get a testing access token as well as the sandbox URL to use the test mode. You can get these information through email after it's finished.

With a testing access token, you'll only be able to access resources created in test mode. With a live access token, you'll only be able to access resources created in live mode.

### Atlas Sandbox <a href="#duffel-airways" id="duffel-airways"></a>

When you search for flights in the test mode, you'll see offers from Atlas Sandbox.&#x20;

The airlines' fares in Sandbox are not as comprehensive and up-to-date as the Production environment. Atlas will not create real bookings or issue real tickets with the airline during the testing process.

### Mock data <a href="#overview" id="overview"></a>

If you want to test the order cancel status, please use these dedicated passenger name in the order request.

<table><thead><tr><th>Ticket Error Code</th><th>Passenger Name</th><th data-hidden></th></tr></thead><tbody><tr><td>601</td><td>ERROR/PRICE</td><td></td></tr><tr><td>604</td><td>ERROR/CARD</td><td></td></tr><tr><td>605</td><td>ERROR/DOCUMENT</td><td></td></tr><tr><td>606</td><td>ERROR/FLIGHT</td><td></td></tr><tr><td>608</td><td>ERROR/DUPLICATE</td><td></td></tr><tr><td>609</td><td>ERROR/MAILBOX</td><td></td></tr></tbody></table>





