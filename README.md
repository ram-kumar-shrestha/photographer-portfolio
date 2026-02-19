# Photographer Portfolio

A full-stack photographer portfolio application built with NestJS backend and React (Vite) frontend.

## Project Structure

```
photographer-portfolio/
├── backend/          # NestJS backend API (Git submodule)
├── frontend/         # React + Vite frontend (Git submodule)
└── README.md         # This file
```

**Note**: The `backend` and `frontend` directories are Git submodules, each with their own repository and detailed README files.

## Prerequisites

Before running this project, make sure you have the following installed:

- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **PostgreSQL** (v12 or higher)
- **Git** (for cloning with submodules)

## Getting Started

### 1. Clone the Repository

This project uses Git submodules for the backend and frontend. Follow these steps to clone the repository with all submodules:

#### Option 1: Clone with submodules in one command

```bash
git clone --recurse-submodules https://github.com/ram-kumar-shrestha/photographer-portfolio.git
cd photographer-portfolio
```

#### Option 2: Clone first, then initialize submodules

```bash
# Clone the main repository
git clone https://github.com/ram-kumar-shrestha/photographer-portfolio.git
cd photographer-portfolio

# Initialize and update submodules
git submodule init
git submodule update
```

#### Option 3: Update submodules if already cloned

If you've already cloned the repository without submodules:

```bash
cd photographer-portfolio
git submodule update --init --recursive
```

After cloning, you should see the `backend/` and `frontend/` directories populated with their respective code.

> **📚 Submodule Documentation**: Each submodule has its own detailed README with specific setup instructions:
>
> - **Backend**: See [backend/README.md](https://github.com/ram-kumar-shrestha/photographer-portfolio-backend/blob/main/README.md) for backend-specific setup
> - **Frontend**: See [frontend/README.md](https://github.com/ram-kumar-shrestha/photographer-portfolio-frontend/blob/main/README.md) for frontend-specific setup

### 2. Set Up Backend

Navigate to the backend directory and install dependencies:

```bash
cd backend
npm install
```

#### Configure Environment Variables

Copy the `.env.example` file to `.env` and update the values:

```bash
cp .env.example .env
```

Update the `.env` file with your database credentials:

```env
APP_MODE=DEVELOPMENT

# Database Configuration
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_USERNAME=postgres
POSTGRES_PASSWORD=your_password
POSTGRES_DB=portfolio

JWT_SECRET=your-secret-jwt-key
```

#### Set Up Database

Make sure PostgreSQL is running and create the database:

```bash
# Create database
createdb portfolio

# Or using psql
psql -U postgres -c "CREATE DATABASE portfolio;"
```

#### Run Database Migrations

```bash
npm run typeorm:migrate
```

#### Start Backend Server

```bash
# Development mode
npm run start:dev

# Production mode
npm run start:prod
```

The backend API will be available at `http://localhost:3000`

### 3. Set Up Frontend

Open a new terminal, navigate to the frontend directory and install dependencies:

```bash
cd frontend
npm install
```

#### Configure Environment Variables

Copy the `.env.example` file to `.env`:

```bash
cp .env.example .env
```

The default configuration should work if your backend is running on port 3000:

```env
VITE_API_BASE_URL=http://localhost:3000
```

#### Start Frontend Development Server

```bash
npm run dev
```

The frontend application will be available at `http://localhost:5173`

## Running the Full Application

1. **Start Backend**: In one terminal, run `cd backend && npm run start:dev`
2. **Start Frontend**: In another terminal, run `cd frontend && npm run dev`
3. **Access Application**: Open your browser and navigate to `http://localhost:5173`

## Features

- User authentication (signup, login, password reset)
- Album management (create, view, update, delete)
- Photo uploads
- User profiles

## Tech Stack

### Backend

- NestJS
- TypeORM
- PostgreSQL
- JWT Authentication

### Frontend

- React
- TypeScript
- Vite
- Axios

## License

MIT
