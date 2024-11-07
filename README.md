# Medium Clone - Blogging Platform

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
