# Football Ticket Booking System – Database Design & SQL Queries

## Project Overview

The Football Ticket Booking System manages football ticket reservations by tracking users, matches, and bookings. The project focuses on:

- **Database Design:** Structuring tables to manage users, football matches, and bookings.
- **ERD Modeling:** Creating an Entity Relationship Diagram (ERD) to visualize the relationships between tables.
- **SQL Queries:** Implementing SQL queries to retrieve and manage data efficiently.

## Key Features

- **Users Table:** Manages information for football fans and ticket managers.
- **Matches Table:** Stores details about football matches, tournament categories, ticket prices, and ticket availability.
- **Bookings Table:** Tracks ticket bookings made by users for specific football matches.

## Database Schema

### 1. Users Table

**Fields:** `user_id`, `full_name`, `email`, `role`, `phone_number`

**Purpose:** Stores information about football fans and ticket managers.

### 2. Matches Table

**Fields:** `match_id`, `fixture`, `tournament_category`, `base_ticket_price`, `match_status`

**Purpose:** Stores information about football matches, including tournament category, ticket prices, and match availability.

### 3. Bookings Table

**Fields:** `booking_id`, `user_id (FK)`, `match_id (FK)`, `seat_number`, `payment_status`, `total_cost`

**Purpose:** Tracks ticket booking details by linking users with football matches.

## Relationships Between Tables

- **User → Bookings:** One user can have many bookings.
- **Match → Bookings:** One match can have many bookings.
- **Booking → User & Match:** Each booking is linked to exactly one user and one football match.

## ERD Design

The Entity Relationship Diagram (ERD) illustrates the relationships between the tables, highlighting:

- **Primary Keys (PK):** Unique identifiers for each record.
- **Foreign Keys (FK):** Ensure referential integrity between tables.
- **Cardinality:** Defines the relationships (One-to-Many, Many-to-One, etc.).

**View the ERD:** *https://lucid.app/lucidchart/2b7ece94-e2f4-4e3c-b97f-77ed9c14cd6c/edit?invitationId=inv_03da49ba-3139-4b96-aedc-d584c53188b3&page=0_0#*

## SQL Queries

### Query 1: Retrieve Available Champions League Matches

**Purpose:** Retrieve all football matches that belong to the **Champions League** and have an **Available** match status.

### Query 2: Search Users by Name

**Purpose:** Use the `LIKE` and `ILIKE` operators to find users whose names start with **Tanvir** or contain **Haque**.

### Query 3: Retrieve Bookings with Missing Payment Status

**Purpose:** Use `IS NULL` and `COALESCE` to display **Action Required** when the payment status is missing.

### Query 4: Retrieve Booking Details with User and Match Information

**Purpose:** Join the **Bookings**, **Users**, and **Matches** tables to retrieve booking details along with the user's full name and the corresponding match fixture.

### Query 5: Display All Users and Their Booking IDs

**Purpose:** Use a **LEFT JOIN** to retrieve every user, including those who have never booked a ticket.

### Query 6: Find Bookings Above the Average Total Cost

**Purpose:** Use a subquery to retrieve bookings where the total cost is higher than the average booking cost.

### Query 7: Retrieve the Top 2 Most Expensive Matches After Skipping the Highest

**Purpose:** Use `ORDER BY`, `OFFSET`, and `LIMIT` to retrieve the second and third most expensive football matches.

## Tools Used

- **PostgreSQL:** Used for creating tables and executing SQL queries.
- **Lucidchart / Draw.io:** Used to design the ERD.

## Design and Implementation Notes

- **Data Integrity:** Enforced through Primary Keys and Foreign Keys.
- **Monetary Values:** Stored using `DECIMAL(10,2)` for accurate ticket price calculations.
- **Constraints:** Unique constraints on user email addresses and `CHECK` constraints on user roles, match status, and payment status ensure valid and consistent data.

## Conclusion

This project demonstrates the design and implementation of a Football Ticket Booking System database. By managing users, matches, and bookings, the system efficiently handles football ticket reservations while maintaining data consistency, referential integrity, and efficient data retrieval through SQL queries.

Feel free to reach out if you have any questions.
