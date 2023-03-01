# Create a Customer Account and Order for a session based ticket with param to send an email receipt

An example of creating a new order using card offline as the payment method. We create a customer account and use this account when we later create the order.

If your test company has tax enabled then tax will be applied to this order at the rate you have set on the ticket.

Sending a `customerAccountID` in the request to `/v2/orders` links the order to the Customer Account.

If the Customer Account has an email address associated with it then sending `sendEmailReceipt=1` when making the request to `/v2/orders` will cause and email receipt to be generated and sent. 

**Please note** by default this collection will not send an email. It generates fake customer data with an email at the `example.com` domain and `sendEmailReceipt=0`

## Request flow

1. Search for sessions valid today for a specific event. Use the first session and the first ticket for that session.
2. Create a new Customer Account 
3. Create a reservation
4. Create an order using the reservation token from the previous step and send an email receipt


## Prerequisites

To run this collection you will need access to a demo company with an API user, and Event with a Session and a Ticket for that Session.

In this example we make a request to get information about the Session filtered by the `eventCatID` (the id of the event) we use `resolve=*` to pull back all connected information about that Session from which we extract the Ticket information. We set `limit=1` so we only return a single Session valid for today.

In reality this step would not be necessary as standing data like this would be usually be synced periodically and then cached locally.

## Set environment variables

Edit your environment to set values for the following variables: 

- apiUrl (e.g. https://api.dtstaging.co.uk)
- apiUser
- apiPassword

(Alternatively create the variables as collection variables)

## Set collection variables

Edit the collection variables specific to this test and set:

- **eventCatID** (the id of the event of the session of the ticket)
- **branchID**



