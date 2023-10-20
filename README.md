# backend-aspdotnet-bookstore
Back end tutorial - Asp.net core API - Scenario 1



𝗧𝗵𝗲 𝗣𝗿𝗼𝗯𝗹𝗲𝗺

I need a system to manage books, customers, orders, and payments.

Only authenticated users can make orders, and only admin users can add or remove books.


𝗧𝗵𝗲 𝗗𝗮𝘁𝗮𝗯𝗮𝘀𝗲 𝗗𝗲𝘀𝗶𝗴𝗻

Books: BookID (PK), Title, Author, Price, Stock

Customers: CustomerID (PK), Name, Email, PasswordHash, IsAdmin

Orders: OrderID (PK), CustomerID (FK), CreatedAt, TotalPrice

OrderItems: OrderItemID (PK), OrderID (FK), BookID (FK), Quantity, Price

Payments: PaymentID (PK), OrderID (FK), PaymentAmount, PaymentDate

A Customer can have many Orders.

An Order can have many OrderItems.

An Order has one Payment.

An OrderItem refers to one Book.


𝗖𝗼𝗻𝗻𝗲𝗰𝘁 𝘁𝗼 𝘁𝗵𝗲 𝗗𝗕

Use an ORM like Entity Framework or Hibernate to map your entities to the database tables.

This will handle the database connections and allow you to work with objects in your code.


𝗔𝗱𝗱 𝗔𝗣𝗜 𝗘𝗻𝗱𝗽𝗼𝗶𝗻𝘁𝘀

GET /books: Retrieve all books.

POST /books: Add a new book (Admin only).

DELETE /books/{bookId}: Delete a book by ID (Admin only).

GET /orders: Retrieve all orders (Admin only).

POST /orders: Create a new order.

GET /orders/{orderId}: Retrieve a specific order.

POST /payments: Process a payment for an order.


𝗔𝗱𝗱 𝗔𝘂𝘁𝗵𝗲𝗻𝘁𝗶𝗰𝗮𝘁𝗶𝗼𝗻

Use JWT (JSON Web Tokens) to handle user authentication.

Users will log in, receive a token, and use that token for the next requests.


𝗟𝗼𝗴𝗴𝗶𝗻𝗴

Configure Serilog to capture and store log entries for monitoring and debugging purposes.


𝗧𝗲𝘀𝘁𝗶𝗻𝗴

Write unit tests and integration tests to verify that your endpoints are working.

Bonus point if you set a Postman collection to test your API.
