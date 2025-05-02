# Assignment 2: Design a Logical Model and Advanced SQL



## Section 1:
You can start this section following *session 1*, but you may want to wait until you feel comfortable wtih basic SQL query writing. 

Steps to complete this part of the assignment:
- Design a logical data model
- Duplicate the logical data model and add another table to it following the instructions
- Write, within this markdown file, an answer to Prompt 3


###  Design a Logical Model

#### Prompt 1
Design a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. 

Additionally, include a date table. 

There are several tools online you can use, I'd recommend [Draw.io](https://www.drawio.com/) or [LucidChart](https://www.lucidchart.com/pages/).

**HINT:** You do not need to create any data for this prompt. This is a conceptual model only. 

#### Prompt 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

#### Prompt 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2? 

**HINT:** search type 1 vs type 2 slowly changing dimensions. 

```
 answer:
 

When managing customer addresses in a bookstore database, there are two main ways to handle address changes, each serving different needs. The first approach, SCD Type 1, is simple and straightforward. Whenever a customer updates their address, the old one is overwritten by the new one, and only the current address is stored. This keeps things easy to manage but means that any past addresses are lost. It’s a good choice when you don’t need to track address history, as it keeps the database clean and simple.

On the other hand, SCD Type 2 is designed to keep a record of every address change. Whenever a customer updates their address, instead of overwriting the old one, a new record is created. This method stores the full history of customer addresses, including when each address was valid, using fields like StartDate, EndDate, and an IsCurrent flag to mark the active address. This approach is helpful for businesses that need to track customer movement or analyze address trends over time.

So, SCD Type 1 is all about simplicity, where the old address is replaced by the new one, while SCD Type 2 allows for a complete history of addresses to be stored. The right choice depends on whether the business values simplicity or needs to maintain detailed historical records.

```

***
