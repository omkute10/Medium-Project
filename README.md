# Medium Project - Blogging Platform

This project is a clone of Medium, a popular blogging platform, built from scratch. It features user-generated content, blog management, user authentication, and responsive design for an optimal reading experience across devices.

## Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [Scripts](#scripts)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

The goal of this project is to build a fully functional blogging website, similar to Medium, with a modern tech stack. The application allows users to read, write, edit, and delete blog posts and provides authentication and user profile management.

## Tech Stack

- **Frontend**: React with TypeScript
- **Backend**: Cloudflare Workers
- **Validation**: Zod
- **ORM**: Prisma with connection pooling
- **Database**: PostgreSQL
- **Authentication**: JSON Web Tokens (JWT)

---

## Features

- **User Authentication**: Sign up, log in, and log out with JWT-based authentication.
- **Blog Management**: Users can create, edit, and delete blog posts.
- **Responsive UI**: User-friendly, mobile-responsive UI built with React.
- **Type Safety**: TypeScript and Zod validation for type-safe frontend development.
- **Database Management**: Prisma ORM for efficient database handling with PostgreSQL.
- **Backend Functions**: Cloudflare Workers to handle backend requests efficiently.

---

## Getting Started

To get a local copy up and running, follow these steps.

### Prerequisites

Ensure you have the following installed:

- Node.js (v14 or above)
- npm or yarn
- PostgreSQL

### Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/medium-clone.git
   cd medium-clone
   ```

2. **Install dependencies**:

   ```bash
   # With npm
   npm install

   # Or with yarn
   yarn install
   ```

3. **Set up the database**:

   - Make sure PostgreSQL is running locally.
   - Create a database for the project.
   - Update the `DATABASE_URL` in `.env` file to match your database settings.

4. **Run Prisma migrations**:

   ```bash
   npx prisma migrate dev --name init
   ```

5. **Start the development server**:

   ```bash
   npm run dev
   ```

---

### Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

```env
DATABASE_URL=postgresql://username:password@localhost:5432/your_database_name
JWT_SECRET=your_jwt_secret
CLOUDFLARE_ACCOUNT_ID=your_cloudflare_account_id
CLOUDFLARE_API_TOKEN=your_cloudflare_api_token
```

---

## Project Structure

```plaintext
medium-clone/
├── public/                 # Static assets
├── src/
│   ├── components/         # React components
│   ├── pages/              # Page components (React Router)
│   ├── services/           # API calls and other services
│   ├── hooks/              # Custom React hooks
│   ├── types/              # TypeScript types
│   ├── utils/              # Utility functions
│   └── validation/         # Zod schemas for data validation
├── prisma/
│   └── schema.prisma       # Prisma schema
├── worker/                 # Cloudflare Workers for backend
├── .env                    # Environment variables
├── .env.example            # Example environment variables
├── package.json
└── README.md
```

---

## Scripts

- **Start Development Server**: `npm run dev`
- **Build Project**: `npm run build`
- **Lint Project**: `npm run lint`
- **Run Tests**: `npm test`
- **Run Migrations**: `npx prisma migrate dev`
- **Generate Prisma Client**: `npx prisma generate`

---

## API Documentation

### Authentication

#### POST `/api/auth/login`

- **Description**: Authenticate a user and return a JWT token.
- **Request Body**:
  ```json
  {
    "email": "user@example.com",
    "password": "yourpassword"
  }
  ```

- **Response**:
  ```json
  {
    "token": "your_jwt_token"
  }
  ```

#### POST `/api/auth/signup`

- **Description**: Register a new user.
- **Request Body**:
  ```json
  {
    "name": "User Name",
    "email": "user@example.com",
    "password": "yourpassword"
  }
  ```

- **Response**:
  ```json
  {
    "id": "user_id",
    "name": "User Name",
    "email": "user@example.com"
  }
  ```

### Blog

#### GET `/api/blogs`

- **Description**: Retrieve all blog posts.
- **Response**:
  ```json
  [
    {
      "id": "blog_id",
      "title": "Blog Title",
      "content": "Blog content...",
      "author": "Author Name",
      "createdAt": "timestamp"
    }
  ]
  ```

#### POST `/api/blogs`

- **Description**: Create a new blog post.
- **Request Body**:
  ```json
  {
    "title": "New Blog Post",
    "content": "Content of the blog..."
  }
  ```

- **Response**:
  ```json
  {
    "id": "blog_id",
    "title": "New Blog Post",
    "content": "Content of the blog...",
    "createdAt": "timestamp"
  }
  ```

*More API routes can be added here for updating and deleting blogs.*

---

## Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a pull request

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
```