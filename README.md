# dbcurrency

A currency converter web app built with **Java 17, Spring Boot 3 and MySQL**. Pick two currencies and an amount; rates come from a MySQL table and the result page shows the converted value.

## Stack

- Spring Boot 3.1 (Web, JDBC, Thymeleaf)
- MySQL (`mysql-connector-j`)
- Maven wrapper (`mvnw`)

## Run locally

1. Create the database and load the sample data:
   ```bash
   mysql -u root -p -e "CREATE DATABASE currency_converter_db"
   mysql -u root -p currency_converter_db < converter_dump/converter_dump.sql
   ```
   The app reads rates from an `exchange_rates` table (`currency_code`, `currency_name`, `country_code`, `conversion_factor`).
2. Set your database credentials:
   ```bash
   export DB_PASSWORD=your_mysql_password
   # optional: DB_URL, DB_USERNAME (default root)
   ```
3. Start it:
   ```bash
   cd dbcurrency
   ./mvnw spring-boot:run
   ```
4. Open http://localhost:8080
