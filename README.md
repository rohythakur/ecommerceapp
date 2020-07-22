# Reviews API

Supports operations for writing reviews and listing reviews for a product but with no sorting or filtering.

### Prerequisites

- MySQL installed and configured to run on localhost, port 3306.
- If you don't want to change application.properties, configure the following settings in your SQL server:
  - Create a database called `ecommerce`.
  - Create a user with "readWrite" access to `ecommerce`.
    - Username = `dev_user`
    - Password = `password`
  - Flyway will create and seed the necessary tables so that you can begin playing with the API immediately on your first run.
    - If you do not want your tables seeded, remove the `V2__SeedTables.sql` file from the db.migration folder.
- MongoDB installed and configured to run on localhost, port 27017.
- If you don't want to change application.properties, configure the following database and collection settings in your Mongo server.
  - Create a database called `ecommerce`.
  - Create a user in the `admin` database with "readWriteAnyDatabase" access.
    - Username = `dev_user`
    - Password = `password`
  - If you want to seed your tables using the same data that Flyway uses to seed the SQL tables, open your cmd shell in the `db.migration` folder.
    - Make sure your mongod service is running.
    - In the cmd shell, type the following command: `mongo --quiet SeedMongoCollection.js`.
      - Alternatively, you can start the mongo interactive shell and type `load("SeedMongoCollection.js")`.
    - The console will print some messages and the data will be seeded.

### API Documentation

- API documentation is created using the Swagger library.
- API documentation can be found at the following URL, once the application itself is running:
  - `http://localhost:8080/swagger-ui.html`

### Technical Notes

#### Database Structure

- Database Name: `ecommerce`
- Tables
  - products
  - reviews
  - comments
- Relationships
  - products to reviews, one-to-many
  - reviews to products, many-to-one
  - reviews to comments, one-to-many
  - comments to reviews, many-to-one

![Database Schema](database_schema.png)
_Database Schema_

### Reference Documentation

For further reference, please consider the following sections:

- [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)

### Guides

The following guides illustrate how to use some features concretely:

- [Accessing JPA Data with REST](https://spring.io/guides/gs/accessing-data-rest/)
- [Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)
- [Accessing data with MySQL](https://spring.io/guides/gs/accessing-data-mysql/)
