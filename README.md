# E-Commerce MERN Project

A MERN-based e-commerce backend for user authentication, password reset, product management, and admin user/product controls.

## Project Structure

```text
backend/
  app.js
  server.js
  config/
  controllers/
  middleware/
  models/
  routes/
  utils/
frontend/
```

The `frontend/` folder is currently empty.

## Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT authentication
- bcryptjs for password hashing
- Nodemailer for email delivery

## Features

- User registration and login
- JWT-based authentication
- User profile and password updates
- Forgot password and reset password flow
- Product listing and product details
- Admin product management
- Product reviews
- Admin user management

## Setup

### Prerequisites

- Node.js
- MongoDB running locally or a MongoDB Atlas connection string
- A Gmail account or SMTP provider for password reset emails

### Install Dependencies

From the project root:

```bash
npm install
```

This installs the backend dependencies defined in the root `package.json`.

### Environment Variables

Create or update `backend/config/config.env` with values similar to the following:

```env
PORT=4000
DB_URI=mongodb://localhost:27017/ecommerce
JWT_SECRET=your_jwt_secret
JWT_EXPIRE=5d
COOKIE_EXPIRE=5
SMPT_SERVICE=gmail
SMPT_MAIL=your_email@gmail.com
SMPT_PASSWORD=your_app_password
SMPT_HOST=smtp.gmail.com
SMPT_PORT=465
```

Notes:

- Keep real credentials out of source control.
- `backend/config/config.env` is ignored by git.
- Replace the MongoDB URI and SMTP values with your own environment details.

## Running the App

### Development

```bash
npm run dev
```

### Production

```bash
npm start
```

The server starts from `backend/server.js` and listens on the port defined in `backend/config/config.env`.

## API Overview

All backend routes are mounted under `/api/v1`.

### User Routes

These routes handle registration, login, profile actions, password updates, password reset, and admin user management.

- `POST /api/v1/register`
- Create a new user account.

- `POST /api/v1/login`
- Log in and receive an authentication cookie.

- `GET /api/v1/logout`
- Clear the auth cookie.

- `POST /api/v1/password/forgot`
- Send a password reset email.

- `PUT /api/v1/password/reset/:token`
- Reset the password with a valid token.

- `GET /api/v1/me`
- Get the authenticated user's profile.

- `PUT /api/v1/password/update`
- Update the authenticated user's password.

- `PUT /api/v1/me/update`
- Update the authenticated user's profile details.

- `GET /api/v1/admin/users`
- Get all users as an admin.

- `GET /api/v1/admin/user/:id`
- Get one user as an admin.

- `PUT /api/v1/admin/user/:id`
- Update a user's role as an admin.

- `DELETE /api/v1/admin/user/:id`
- Delete a user as an admin.

### Product Routes

These routes handle product browsing, admin product management, and reviews.

- `GET /api/v1/products`
- Get all products.

- `GET /api/v1/product/:id`
- Get product details by ID.

- `POST /api/v1/admin/product/new`
- Create a product as an admin.

- `PUT /api/v1/admin/product/:id`
- Update a product as an admin.

- `DELETE /api/v1/admin/product/:id`
- Delete a product as an admin.

- `PUT /api/v1/review`
- Add or update a product review.

## Notes

- Authentication is handled with JWT stored in an HTTP-only cookie.
- Email/password reset logic is implemented in the backend.
- The `frontend/` folder is currently empty.

## License

ISC
