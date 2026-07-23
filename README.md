# E-Commerce MERN Project

A MERN-based e-commerce backend with user authentication, product management, and password reset flows.

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

## Getting Started

### Prerequisites

- Node.js
- MongoDB running locally or a MongoDB Atlas connection string

### Install Dependencies

From the project root:

```bash
npm install
```

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

Note: keep real credentials out of source control.

## Running the Project

### Development

```bash
npm run dev
```

### Production

```bash
npm start
```

The server starts from `backend/server.js` and listens on the port defined in `backend/config/config.env`.

## API Base Path

All routes are mounted under `/api/v1`.

### User Routes

- `POST /api/v1/register`
- `POST /api/v1/login`
- `GET /api/v1/logout`
- `POST /api/v1/password/forgot`
- `PUT /api/v1/password/reset/:token`
- `GET /api/v1/me`
- `PUT /api/v1/password/update`
- `PUT /api/v1/me/update`
- `GET /api/v1/admin/users`
- `GET /api/v1/admin/user/:id`
- `PUT /api/v1/admin/user/:id`
- `DELETE /api/v1/admin/user/:id`

### Product Routes

- `GET /api/v1/products`
- `GET /api/v1/product/:id`
- `POST /api/v1/admin/product/new`
- `PUT /api/v1/admin/product/:id`
- `DELETE /api/v1/admin/product/:id`
- `PUT /api/v1/review`

## Notes

- Authentication is handled with JWT stored in an HTTP-only cookie.
- Email/password reset logic is implemented in the backend.
- The app currently has no frontend implementation.

## License

ISC
