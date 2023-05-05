# ACIDPostgreSQL Project

This project demonstrates the use of ACID (Atomicity, Consistency, Isolation, Durability) properties in PostgreSQL using Java JDBC.

## Overview

The ACIDPostgreSQL project provides a Java program that showcases the atomicity, consistency, isolation, and durability features of PostgreSQL database transactions. It performs various operations on three tables: Product, Depot, and Stock, demonstrating the behavior of ACID properties.

## Prerequisites

To run this project, you need to have the following:

- Java Development Kit (JDK)
- PostgreSQL database
- PostgreSQL JDBC driver

## Installation

1. Clone the repository to your local machine:

   ```shell
   git clone https://github.com/your-username/ACIDPostgreSQL.git
   ```

2. Configure the PostgreSQL database:

   - Create a new database named "CS623ProjectTeam1" in your PostgreSQL server.

3. Update database credentials:

   - Open the `ACIDPostgreSQL.java` file.
   - Locate the following line:

     ```java
     Connection conn = DriverManager.getConnection("jdbc:postgresql://localhost:5432/CS623ProjectTeam1", "postgres", "rahul.1996");
     ```

   - Modify the connection URL, username, and password according to your PostgreSQL configuration.

4. Import required libraries:

   - Make sure you have the PostgreSQL JDBC driver (JAR file) added to your project's classpath.

5. Build and run the project:

   - Compile the Java file:

     ```shell
     javac -cp path/to/postgresql.jar ACIDPostgreSQL.java
     ```

   - Run the program:

     ```shell
     java -cp path/to/postgresql.jar:. ACIDPostgreSQL
     ```

6. Verify the results:

   - The program will execute various SQL statements, demonstrating the behavior of ACID properties.
   - Check your PostgreSQL database to observe the changes made during the transactions.

## Explanation

The `ACIDPostgreSQL.java` file contains the main code for this project. It performs the following steps:

1. Loads the PostgreSQL JDBC driver.

2. Establishes a connection to the PostgreSQL database.

3. Disables auto-commit to enable transaction handling.

4. Sets the transaction isolation level to `TRANSACTION_SERIALIZABLE` for consistency and isolation.

5. Creates the required tables (`Product`, `Depot`, and `Stock`) if they don't exist already.

6. Resets the data in the tables by deleting all existing records.

7. Inserts sample data into the tables.

8. Begins the transaction.

9. Executes various SQL statements that represent different transactions.

10. If an exception occurs during the execution of SQL statements, it rolls back the changes made in the transaction.

11. Commits the changes if no exception occurs.

12. Closes the database connection and releases resources.
