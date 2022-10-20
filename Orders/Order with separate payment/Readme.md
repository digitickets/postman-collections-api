# Make a reservation and an unpaid order with a separate payment

An example of creating a new unpaid order and then making a separate API request to add a cash payment to the order.

If your test company has tax enabled then tax will be applied to this order at the rate you have set on the ticket.

## Request flow

1. Add products to the cart
2. Create a reservation
3. Create an order using the reservation token from the previous step
4. Make a payment request using the orderID of the unpaid order



## Prerequisites

To run this collection you will need access to a demo company with an API user and a Ticket.

In this example we make a request to get information about the ticket such as price which is then used in the reservation request. In reality this step would not be necessary as standing data like this would be usually be synced periodically and then cached locally.

## Set environment variables

Edit your environment to set values for the following variables: 

- apiUrl (e.g. https://api.dtstaging.co.uk)
- apiUser
- apiPassword

(Alternatively create the variables as collection variables)

## Set collection variables

Edit the collection variables specific to this test and set:

- **ticketID** (the id of a ticket to purchase)
- **branchID**



