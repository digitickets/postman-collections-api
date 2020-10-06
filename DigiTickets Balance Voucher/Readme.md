#Using a DigiTickets Balance Voucher

An example of creating a new order using a DigiTickets Balance Voucher as a payment method.

A DigiTickets voucher is a payment method not a type of discount. Use it as you would any other type of payment method. 

In order to get information about a specific voucher in order to check the balance for example, you need to make an authenticated request to the `/v2/soldgiftvouchers` api endpoint passing the 16 character voucher reference in the `ref` param.

**NOTE** A request for an invalid voucher will return `[]` a request for a valid voucher code will return the details of that voucher. It is up to you as a developer to check currentBalance, status, expiredAt, etc. to decide how you would like to handle the voucher.

##Prerequisites

To run this collection you will need access to a demo company with an API user, a Ticket, and an existing Balance Voucher ready to be used for payment. You will then need to have sold a Balance Voucher in order to create a Sold Balance Gift Voucher that you can then use for payment.

##Set environment variables

Edit your environment to set values for the following variables: 

- apiUrl (e.g. https://api.dtstaging.co.uk)
- apiUser
- apiPassword

(Alternatively create the variables as collection variables)

##Set collection variables

Edit the collection variables specific to this test and set:

- **voucherRef** (the ref of an existing balance voucher that has already been sold to use as the payment method)
- **ticketID** (the id of a ticket to purchase)



