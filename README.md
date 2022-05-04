# E-Commerce Back End : Object-Relational Mapping (ORM)

## Description

The back end for an e-commerce site configuring a Express.js API to use Sequelize to interact with a MySQL database.

## Acceptance Criteria

```md
A functional Express.js API

- Adding database name, MySQL username, and MySQL password to an environment variable file connects to a database using Sequelize
- Entering schema and seed commands a development database is created and is seeded with test data
- Entering the command to invoke the application a server is started and the Sequelize models are synced to the MySQL database
- Opening API GET routes in Insomnia Core for categories, products, or tags displays the data for each of these routes in a formatted JSON
- Ablility to successfully create, update, and delete data in the database by testing API POST, PUT, and DELETE routes in Insomnia Core
```

Use of the [MySQL2](https://www.npmjs.com/package/mysql2) and [Sequelize](https://www.npmjs.com/package/sequelize) packages to connect Express.js API to a MySQL database and the [dotenv](https://www.npmjs.com/package/dotenv) package to use environment variables to store sensitive data.

A `schema.sql` file in the `db` folder is used to create a database with MySQL shell commands. Environment variables are used to store sensitive data like your MySQL username, password, and database name.

### Database Models

A database contains the following four models, including the requirements listed for each model:

- `Category`

  - `id`

    - Integer.

    - Doesn't allow null values.

    - Set as primary key.

    - Uses auto increment.

  - `category_name`

    - String.

    - Doesn't allow null values.

- `Product`

  - `id`

    - Integer.

    - Doesn't allow null values.

    - Set as primary key.

    - Uses auto increment.

  - `product_name`

    - String.

    - Doesn't allow null values.

  - `price`

    - Decimal.

    - Doesn't allow null values.

    - Validates that the value is a decimal.

  - `stock`

    - Integer.

    - Doesn't allow null values.

    - Set a default value of `10`.

    - Validates that the value is numeric.

  - `category_id`

    - Integer.

    - References the `Category` model's `id`.

- `Tag`

  - `id`

    - Integer.

    - Doesn't allow null values.

    - Set as primary key.

    - Uses auto increment.

  - `tag_name`

    - String.

- `ProductTag`

  - `id`

    - Integer.

    - Doesn't allow null values.

    - Set as primary key.

    - Uses auto increment.

  - `product_id`

    - Integer.

    - References the `Product` model's `id`.

  - `tag_id`

    - Integer.

    - References the `Tag` model's `id`.

### Associations

Association methods on Sequelize models create the following relationships between them:

- `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

- `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Allow products to have multiple tags and tags to have many products by using the `ProductTag` through model.

### API Routes to Perform RESTful CRUD Operations

Finished routes in `product-routes.js`, `tag-routes.js`, and `category-routes.js` perform create, read, update, and delete operations using Sequelize models.

## Review

You are required to submit BOTH of the following for review:

- A walkthrough video demonstrating the functionality of the application and all of the acceptance criteria being met.

- The URL of the GitHub repository. Give the repository a unique name and include a readme describing the project.

## https://github.com/JervanSahd/E-Commerce-Back-End

Steve Snavely
