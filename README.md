

# House Cleaning App

This is a house cleaning app that allows users to schedule cleaning jobs and manage their cleaning requests. It provides different functionalities for customers, cleaners, and admin users.

## Models

### User

| Field           | Type    | Description                             |
| --------------- | ------- | --------------------------------------- |
| id              | integer | Primary key                             |
| name            | string  | Name of the user                        |
| email           | string  | Unique email address for login          |
| password_digest | string  | Securely stored hashed password         |
| role            | string  | User's role (e.g., 'customer' or 'cleaner') |

### CleaningPlan

| Field        | Type    | Description                   |
| ------------ | ------- | ----------------------------- |
| id           | integer | Primary key                   |
| name         | string  | Name of the cleaning plan     |
| description  | text    | Description of the plan       |
| price        | decimal | Cost of the cleaning plan     |

### Cleaner

| Field          | Type    | Description                 |
| -------------- | ------- | --------------------------- |
| id             | integer | Primary key                 |
| name           | string  | Name of the cleaner         |
| specialization | string  | Area of expertise           |

### Review

| Field      | Type    | Description                               |
| ---------- | ------- | ----------------------------------------- |
| id         | integer | Primary key                               |
| rating     | integer | Rating given by the customer (1-5 stars)  |
| comment    | text    | Optional comment or review from the customer |
| user_id    | integer | Foreign key referencing the customer User |
| cleaner_id | integer | Foreign key referencing the User (cleaner) |

### CleaningRequest

| Field       | Type    | Description                                    |
| ----------- | ------- | ---------------------------------------------- |
| id          | integer | Primary key                                    |
| user_id     | integer | Foreign key referencing the customer User     |
| cleaner_id  | integer | Foreign key referencing the User (cleaner)    |
| accepted    | boolean | Indicates if the cleaning request is accepted by the cleaner |
| deleted     | boolean | Indicates if the cleaning request is deleted, i.e., not accepted by any cleaner |

Feel free to use this information to set up your models in the house cleaning app. Additionally, don't forget to create appropriate associations between the models using Active Record in Rails to establish the relationships effectively.
