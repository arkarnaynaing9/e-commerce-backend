# E-Commerce API

This is a backend API for an e-commerce platform built using Laravel. The API provides user registration, login, and CRUD operations for products, orders, and users. It has role-based authentication where admin users can manage products, orders, and users, while regular users can view and purchase products.

## Features

- User Authentication (Register, Login, Logout)
- Role-Based Access Control (Admin vs User)
- Admin CRUD Operations for Products, Orders, and Users
- User CRUD Operations for Products and Orders
- Sanctum-based Authentication for API security
- RESTful API routes for product and order management

## Technologies Used

- **Laravel**: PHP framework for building the backend.
- **Sanctum**: For API token authentication.
- **MySQL**: Database to store user, product, and order data.
- **API Routes**: For communication between client and server.

   AI-assisted coding-ChatGPT

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/ecommerce-api.git
    cd ecommerce-api
    ```

2. Install dependencies:

    ```bash
    composer install
    ```

3. Set up your `.env` file (you can copy `.env.example`):

    ```bash
    cp .env.example .env
    ```

4. Generate the application key:

    ```bash
    php artisan key:generate
    ```

5. Configure your database connection in the `.env` file.

6. Run the database migrations to set up the tables:

    ```bash
    php artisan migrate
    ```

7. Optionally, seed your database with sample data:

    ```bash
    php artisan db:seed
    ```

8. Serve the application:

    ```bash
    php artisan serve
    ```

Now, the API should be accessible at `http://localhost:8000`.

## API Endpoints

### Authentication

- **POST** `/api/register`: Register a new user (returns user data and API token).
- **POST** `/api/login`: Login an existing user (returns user data and API token).
- **POST** `/api/logout`: Logout the authenticated user.

### Admin Routes (Requires Admin Role)

- **GET** `/api/admin/products`: List all products.
- **POST** `/api/admin/products`: Create a new product.
- **GET** `/api/admin/products/{product}`: View a product.
- **PUT** `/api/admin/products/{product}`: Update a product.
- **DELETE** `/api/admin/products/{product}`: Delete a product.

- **GET** `/api/admin/orders`: List all orders.
- **GET** `/api/admin/orders/{order}`: View an order.
- **POST** `/api/admin/orders`: Create a new order.
- **PUT** `/api/admin/orders/{order}`: Update an order.
- **DELETE** `/api/admin/orders/{order}`: Delete an order.

- **GET** `/api/admin/users`: List all users.
- **POST** `/api/admin/users`: Create a new user.
- **GET** `/api/admin/users/{user}`: View a user.
- **PUT** `/api/admin/users/{user}`: Update a user.
- **DELETE** `/api/admin/users/{user}`: Delete a user.

### User Routes

- **GET** `/api/user/products`: List all products.
- **GET** `/api/user/products/{product}`: View a product.

- **POST** `/api/user/orders`: Create a new order.
- **GET** `/api/user/orders`: List all orders for the authenticated user.
- **GET** `/api/user/orders/{order}`: View a specific order.

## Authentication & Authorization

This API uses Laravel Sanctum for token-based authentication. Users must provide a valid API token in the `Authorization` header for protected routes.

Example:

```bash
Authorization: Bearer {your_api_token}
