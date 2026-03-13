# Example Postman Collections for the DigiTickets API

This repo contains code examples (collections) designed to be used with [Postman](https://www.postman.com/) that are designed to help you to use the DigiTickets API.

A [Postman Collection](https://learning.postman.com/docs/postman/collections/) is a group of API requests together which you may also be able to run sequentially to demonstrate a sequence of API calls.

## How to use

### 1. Create a test company

In order to make use of these examples you will need access to test company. 

If you do not have a test company please [contact DigiTickets](https://www.digitickets.co.uk/contact).

Depending on the nature of the collections that you wish to use you will need to create Categories, Tickets, Products, etc. in your test company. 

### 2. Import the collections into Postman
You will need to import the collections that you want to use into Postman.

You can also use the `DigiTicketsAPI.postman_environment.json` file which will need to be populated with:
- apiUser
- apiPassword
- apiUrl

Values such as ticketIDs from your test company can be used as 'collection variables' to allow you to run and work with the collections.

## Order flows

### Confirmed Order Flow
The existing process of creating orders detailed in **/Orders** 

- Orders created this way are confirmed automatically.
- Payments can be sent as part of the order creation request.

### Unconfirmed Order Flow
The new order flow detailed in **/Unconfirmed Order Flow**

- Orders created this way are unconfirmed
- You must confirm the order with additional request
- Payments should be sent in a separate request




