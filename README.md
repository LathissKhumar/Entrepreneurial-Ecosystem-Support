# CITBIF - Center for Innovation and Technology Business Incubation Forum

A comprehensive platform for startup incubation and innovation management, built with React + TypeScript (Frontend) and Node.js + Express + PostgreSQL (Backend).

## 🚀 Quick Start

> **📖 For a detailed step-by-step guide, see [QUICK_START.md](./QUICK_START.md)**

### Prerequisites
- Node.js (v18 or higher)
- PostgreSQL (v14 or higher)
- npm or yarn

### One-Command Setup & Run

1. **Install dependencies and setup:**
   ```bash
   npm run install:all
   npm run setup
   ```

2. **Start both frontend and backend:**
   ```bash
   npm start
   ```

That's it! Your application will be available at:
- **Frontend:** http://localhost:5173
- **Backend:** http://localhost:5000

## ✨ Key Features

### 🔐 User Management & Authentication
- **JWT-based Authentication**: Secure login/logout with refresh tokens
- **Multi-role Support**: Individual, Enterprise, and Admin roles
- **Profile Management**: Comprehensive user profiles with completion tracking
- **Email Verification**: Account verification system
- **Session Management**: Secure session handling with tracking

### 🚀 Startup Incubation Platform
- **Multi-step Application Process**: 6-step wizard for startup registration
- **TRL Assessment**: Technology Readiness Level tracking
- **Application Status Management**: Draft, Submitted, Under Review, Approved/Rejected
- **Document Management**: Secure file uploads for required documents
- **Funding Information**: Track funding stages, amounts, and sources
- **Milestone Tracking**: Progress monitoring and goal setting

### 👥 Ecosystem Management
- **Mentor Network**: Comprehensive mentor profiles with expertise matching
- **Investor Relations**: Investor profiles with investment preferences
- **Event Management**: Create, manage, and track startup events and workshops
- **Document Repository**: Centralized document storage and organization
- **Reporting System**: Analytics and report generation

### 🎯 Specialized Features
- **Innovation vs Incubation**: Support for different startup types
- **Multi-step Profile Wizard**: Guided onboarding process
- **Previous Incubation Tracking**: Track prior incubation history
- **Sector Classification**: Industry-specific categorization
- **Real-time Notifications**: System-wide notification management
- **Admin Dashboard**: Comprehensive administrative controls

## 📋 Available Commands

### Development Commands
- `npm start` - Smart start script (installs backend deps if needed, then starts both servers)
- `npm run dev:all` - Start both frontend and backend using concurrently
- `npm run dev:frontend` - Start only the React frontend (port 5173)
- `npm run dev:backend` - Start only the Node.js backend (port 5000)

### Setup Commands
- `npm run setup` - Initial setup: creates .env, uploads folder, checks dependencies
- `npm run install:all` - Install dependencies for both frontend and backend

### Production Commands
- `npm run build:all` - Build both frontend and backend for production
- `npm run start:all` - Start both frontend and backend in production mode

### Individual Frontend Commands
- `npm run dev` - Start frontend only (default Vite command)
- `npm run build` - Build frontend only
- `npm run preview` - Preview built frontend
- `npm run lint` - Run ESLint on frontend

### Backend Commands (run from backend/ directory)
- `cd backend && npm run dev` - Start backend development server with hot reload
- `cd backend && npm run build` - Build backend TypeScript to JavaScript
- `cd backend && npm start` - Start production backend server
- `cd backend && npm test` - Run backend tests with Jest
- `cd backend && npm run lint` - Run ESLint on backend
- `cd backend && npm run lint:fix` - Fix ESLint errors automatically

### Database Commands (run from backend/ directory)
- `cd backend && npx prisma generate` - Generate Prisma client
- `cd backend && npx prisma migrate dev` - Run database migrations
- `cd backend && npx prisma studio` - Open Prisma Studio (database GUI)
- `cd backend && npm run seed` - Seed database with initial data
- `cd backend && npm run seed:admin` - Create admin user

## 🛠️ Tech Stack

### Frontend Technologies
- **Framework**: React 18.3.1 with TypeScript
- **Build Tool**: Vite 7.1.6 (fast build and hot reload)
- **Styling**: Tailwind CSS 3.4.1 with PostCSS
- **Routing**: React Router DOM 7.9.1
- **HTTP Client**: Axios 1.12.2
- **Icons**: Lucide React 0.344.0
- **State Management**: React Context API
- **UI Components**: Custom components with Tailwind

### Backend Technologies
- **Runtime**: Node.js (v18+)
- **Framework**: Express.js 4.21.2 with TypeScript
- **Database ORM**: Prisma 5.22.0 (Primary)
- **Database**: PostgreSQL (Primary) / MongoDB (Alternative with Mongoose 8.18.1)
- **Authentication**: JSON Web Tokens (JWT) 9.0.2
- **Password Hashing**: bcryptjs 2.4.3
- **Validation**: Joi 17.11.0 + Express Validator 7.0.1
- **File Upload**: Multer 1.4.5-lts.1
- **Email**: Nodemailer 6.9.7
- **Security**: Helmet 7.1.0, CORS 2.8.5, Rate Limiting 7.1.5
- **Logging**: Morgan 1.10.0
- **Environment**: dotenv 16.3.1

### Development Tools
- **Language**: TypeScript 5.5.3 (Frontend) / 5.3.2 (Backend)
- **Linting**: ESLint 9.9.1 with TypeScript support
- **Testing**: Jest 29.7.0 with ts-jest and supertest
- **Development**: Nodemon 3.0.2, Concurrently 9.2.1
- **Database GUI**: Prisma Studio
- **Process Manager**: start-dev.js (custom smart starter)

### Database Schema (PostgreSQL with Prisma)
- **Users**: Authentication, roles, profiles
- **Startups**: Applications, status tracking, milestones
- **Mentors**: Profiles, expertise, availability
- **Investors**: Profiles, investment preferences
- **Events**: Event management and registration
- **Documents**: File storage and metadata
- **Reports**: Analytics and report generation
- **Notifications**: User notification system
- **Sessions**: JWT session management

### Additional Features
- **Multi-role Support**: Individual, Enterprise, Admin
- **File Upload Security**: Type validation, size limits
- **Real-time Features**: Live notifications, status updates
- **Admin Dashboard**: Comprehensive management interface
- **API Proxy**: Vite dev server proxies API calls
- **Environment Flexibility**: Supports both PostgreSQL and MongoDB
- **Docker Support**: docker-compose.yml for service orchestration

## 🏗️ Project Structure

```
citbif/
├── src/                          # Frontend (React + TypeScript + Vite)
│   ├── components/               # React components
│   │   ├── auth/                 # Authentication components
│   │   ├── dashboard/            # Dashboard components
│   │   │   ├── admin/            # Admin dashboard
│   │   │   └── startup/          # Startup dashboard
│   │   ├── layout/               # Layout components
│   │   ├── profile/              # Profile management
│   │   │   └── steps/            # Multi-step profile wizard
│   │   └── ui/                   # Reusable UI components
│   ├── context/                  # React contexts (Auth, Alerts)
│   ├── hooks/                    # Custom React hooks
│   ├── services/                 # API services and mock APIs
│   └── types/                    # TypeScript type definitions
├── backend/                      # Backend API (Node.js + Express + TypeScript)
│   ├── src/
│   │   ├── config/              # Configuration (env, database, Prisma)
│   │   ├── middleware/          # Express middleware
│   │   ├── models/              # Database models (Mongoose/alternative)
│   │   ├── routes/              # API routes (auth, users, startups, etc.)
│   │   ├── scripts/             # Utility scripts (seeding, etc.)
│   │   ├── tests/               # Test files
│   │   ├── types/               # TypeScript types
│   │   └── utils/               # Utility functions (JWT, email, helpers)
│   ├── prisma/                  # Prisma ORM (PostgreSQL)
│   │   ├── migrations/          # Database migrations
│   │   ├── schema.prisma        # Database schema
│   │   └── seed.ts              # Database seeding
│   ├── env.example              # Environment variables template
│   ├── jest.config.js           # Jest testing configuration
│   ├── nodemon.json             # Nodemon configuration
│   ├── tsconfig.json            # TypeScript configuration
│   └── package.json             # Backend dependencies
├── package.json                 # Root package.json with unified scripts
├── setup.js                     # Initial setup script
├── start-dev.js                 # Smart development starter
├── vite.config.ts               # Vite configuration
├── tailwind.config.js           # Tailwind CSS configuration
├── tsconfig.json                # Frontend TypeScript configuration
├── QUICK_START.md               # Quick start guide
└── docker-compose.yml           # Docker compose for services
```

## 🔧 Configuration

### Frontend Configuration
The frontend uses Vite and is configured in `vite.config.ts`. Key configurations:
- **Development Server**: Runs on port 5173 with hot reload
- **API Proxy**: Automatically proxies `/api` calls to backend (port 5000)
- **React + TypeScript**: Full TypeScript support with React 18
- **Tailwind CSS**: Utility-first CSS framework

### Backend Configuration
The backend configuration is in `backend/env.example`. Key environment variables:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database Configuration (PostgreSQL with Prisma)
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/citbif

# Alternative MongoDB Support (if using Mongoose models)
MONGODB_URI=mongodb://localhost:27017/CITBIF
MONGODB_TEST_URI=mongodb://localhost:27017/CITBIF_test

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key-here
JWT_EXPIRES_IN=7d
JWT_REFRESH_EXPIRES_IN=30d

# Email Configuration (Nodemailer)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
FROM_EMAIL=noreply@citbif.com
FROM_NAME=CITBIF Platform

# File Upload Configuration (Multer)
MAX_FILE_SIZE=10485760
UPLOAD_PATH=./uploads
ALLOWED_FILE_TYPES=pdf,doc,docx,jpg,jpeg,png

# CORS Configuration
CORS_ORIGIN=http://localhost:5173
CORS_CREDENTIALS=true

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100

# Admin Configuration
ADMIN_EMAIL=admin@citbif.com
ADMIN_PASSWORD=admin123

# Application URLs
FRONTEND_URL=http://localhost:5173
BACKEND_URL=http://localhost:5000
```

### Database Setup
The project supports both PostgreSQL (primary) and MongoDB:

**PostgreSQL with Prisma** (Recommended):
```bash
# Install PostgreSQL and create database
createdb citbif

# Run Prisma migrations
cd backend && npx prisma migrate dev

# Generate Prisma client
npx prisma generate

# Seed the database
npm run seed
```

**MongoDB** (Alternative):
```bash
# Start MongoDB service
sudo systemctl start mongod

# Database will be created automatically on first connection
```

## 📚 API Documentation

### Authentication Endpoints
- `POST /api/auth/login` - User login with JWT token
- `POST /api/auth/signup` - User registration and account creation
- `POST /api/auth/logout` - User logout and session termination
- `POST /api/auth/refresh` - Refresh JWT access token
- `GET /api/auth/me` - Get current authenticated user profile

### User Management
- `GET /api/users` - Get all users (admin only)
- `GET /api/users/:id` - Get user by ID
- `PUT /api/users/:id` - Update user profile
- `DELETE /api/users/:id` - Delete user account (admin only)

### Startup Management
- `GET /api/startups` - Get all startups (with filtering options)
- `POST /api/startups` - Create new startup application
- `GET /api/startups/:id` - Get startup details by ID
- `PUT /api/startups/:id` - Update startup information
- `DELETE /api/startups/:id` - Delete startup application
- `POST /api/startups/:id/milestones` - Add/update startup milestones
- `GET /api/startups/:id/status` - Get application status and progress

### Mentor Network
- `GET /api/mentors` - Get all mentor profiles
- `POST /api/mentors` - Create new mentor profile
- `GET /api/mentors/:id` - Get mentor details by ID
- `PUT /api/mentors/:id` - Update mentor profile
- `DELETE /api/mentors/:id` - Delete mentor profile
- `POST /api/mentors/:id/availability` - Update mentor availability
- `GET /api/mentors/search` - Search mentors by expertise/sector

### Investor Relations
- `GET /api/investors` - Get all investor profiles
- `POST /api/investors` - Create new investor profile
- `GET /api/investors/:id` - Get investor details by ID
- `PUT /api/investors/:id` - Update investor profile
- `DELETE /api/investors/:id` - Delete investor profile
- `GET /api/investors/search` - Search investors by focus areas

### Event Management
- `GET /api/events` - Get all events (with date filtering)
- `POST /api/events` - Create new event
- `GET /api/events/:id` - Get event details by ID
- `PUT /api/events/:id` - Update event information
- `DELETE /api/events/:id` - Delete event
- `POST /api/events/:id/register` - Register for an event
- `DELETE /api/events/:id/register` - Unregister from event

### Document Management
- `GET /api/documents` - Get user's documents
- `POST /api/documents/upload` - Upload new document
- `GET /api/documents/:id` - Get document details by ID
- `GET /api/documents/:id/download` - Download document file
- `DELETE /api/documents/:id` - Delete document
- `PUT /api/documents/:id` - Update document metadata

### Reports & Analytics
- `GET /api/reports` - Get available reports
- `POST /api/reports/generate` - Generate new report
- `GET /api/reports/:id` - Get report details by ID
- `GET /api/reports/:id/download` - Download report file
- `DELETE /api/reports/:id` - Delete report

### Notifications
- `GET /api/notifications` - Get user notifications
- `PUT /api/notifications/:id/read` - Mark notification as read
- `DELETE /api/notifications/:id` - Delete notification
- `POST /api/notifications/mark-all-read` - Mark all notifications as read

### Admin Panel
- `GET /api/admin/dashboard` - Get admin dashboard statistics
- `GET /api/admin/users` - Get all users with admin controls
- `PUT /api/admin/users/:id/role` - Update user role
- `GET /api/admin/startups` - Get all startups for review
- `PUT /api/admin/startups/:id/status` - Update startup application status

## 🌐 Application URLs

- **Frontend:** http://localhost:5173
- **Backend API:** http://localhost:5000
- **API Health Check:** http://localhost:5000/health
- **Prisma Studio:** http://localhost:5555 (when running `npx prisma studio`)

## 🧪 Testing

### Backend Testing
The backend includes comprehensive testing with Jest and Supertest:

```bash
# Run all backend tests
cd backend && npm test

# Run tests in watch mode
cd backend && npm run test:watch

# Run tests with coverage
cd backend && npm run test:coverage
```

**Test Coverage Includes:**
- Authentication endpoints
- CRUD operations for all models
- Middleware validation
- Database operations
- File upload functionality
- API error handling

### Frontend Testing
Frontend testing is currently not configured but can be added:

```bash
# Install testing dependencies (optional)
npm install -D @testing-library/react @testing-library/jest-dom vitest

# Run frontend tests (when configured)
npm test
```

### Database Testing
- **Test Database**: Uses separate test database (MongoDB/PostgreSQL)
- **Test Data**: Automated test data creation and cleanup
- **Migration Testing**: Prisma migration testing in CI/CD

## 🚀 Deployment

### Prerequisites for Deployment
- PostgreSQL database (cloud or self-hosted)
- Node.js runtime environment
- Environment variables configured
- Domain/subdomain for the application

### Frontend Deployment
```bash
# Build the frontend
npm run build

# The 'dist' folder contains the built static files
# Deploy to any static hosting service:
# - Vercel, Netlify, AWS S3 + CloudFront
# - GitHub Pages, Firebase Hosting
```

### Backend Deployment

**Option 1: Traditional Server Deployment**
```bash
cd backend

# Install production dependencies
npm ci --only=production

# Build TypeScript to JavaScript
npm run build

# Run database migrations
npx prisma migrate deploy

# Generate Prisma client for production
npx prisma generate

# Start with process manager (PM2 recommended)
pm2 start dist/index.js --name "citbif-api"

# Or start directly
npm start
```

**Option 2: Docker Deployment**
```bash
# Use the included docker-compose.yml
docker-compose up -d

# Or build custom Docker image
docker build -t citbif-backend ./backend
docker run -p 5000:5000 citbif-backend
```

**Option 3: Cloud Platform Deployment**
- **Heroku**: Includes Procfile support
- **Railway**: Direct GitHub deployment
- **AWS/GCP/Azure**: Container or serverless deployment
- **DigitalOcean App Platform**: Automatic deployment

### Environment Configuration for Production
```env
# Update these for production
NODE_ENV=production
PORT=5000
DATABASE_URL=postgresql://user:password@host:port/database
JWT_SECRET=secure-random-string-for-production
CORS_ORIGIN=https://your-frontend-domain.com
FRONTEND_URL=https://your-frontend-domain.com
```

### Database Deployment
- **Cloud PostgreSQL**: AWS RDS, Google Cloud SQL, Azure Database
- **Managed Services**: Supabase, PlanetScale, Neon
- **Self-hosted**: PostgreSQL on VPS with proper backups

### Security Considerations
- Use environment variables for all secrets
- Enable HTTPS in production
- Configure proper CORS origins
- Set up database connection pooling
- Enable request rate limiting
- Use secure JWT secrets (256-bit minimum)

## 🤝 Contributing

We welcome contributions to the CITBIF platform! Here's how to get started:

### Development Setup
1. **Fork the repository** on GitHub
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Entrepreneurial-Ecosystem-Support.git
   cd Entrepreneurial-Ecosystem-Support
   ```
3. **Install dependencies**:
   ```bash
   npm run install:all
   npm run setup
   ```
4. **Set up database**:
   ```bash
   cd backend
   npx prisma migrate dev
   npm run seed
   ```

### Development Workflow
1. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```
2. **Make your changes** following the coding standards
3. **Test your changes**:
   ```bash
   # Test backend
   cd backend && npm test
   
   # Test frontend (manual testing for now)
   npm start
   ```
4. **Lint your code**:
   ```bash
   npm run lint
   cd backend && npm run lint
   ```
5. **Commit and push**:
   ```bash
   git add .
   git commit -m "feat: add your feature description"
   git push origin feature/your-feature-name
   ```
6. **Submit a pull request** with a clear description

### Coding Standards
- **TypeScript**: Use strict TypeScript throughout
- **ESLint**: Follow the configured ESLint rules
- **Prisma**: Use Prisma for database operations
- **API Design**: Follow RESTful API principles
- **Error Handling**: Implement proper error handling
- **Security**: Follow security best practices

### Project Structure Guidelines
- Keep components small and focused
- Use TypeScript types for all data structures
- Follow the established folder structure
- Write meaningful commit messages
- Add comments for complex business logic

### Issues and Bug Reports
- Use GitHub Issues for bug reports and feature requests
- Include detailed reproduction steps for bugs
- Tag issues appropriately (bug, enhancement, question)
- Search existing issues before creating new ones

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🆘 Support & Documentation

### Getting Help
- **Quick Start Guide**: See [QUICK_START.md](./QUICK_START.md) for rapid setup
- **Backend API Docs**: See [backend/README.md](./backend/README.md) for API details
- **GitHub Issues**: Report bugs and request features
- **Discussions**: Use GitHub Discussions for questions and ideas

### Useful Links
- **Frontend**: React + TypeScript + Vite + Tailwind CSS
- **Backend**: Node.js + Express + Prisma + PostgreSQL
- **Development**: Hot reload, ESLint, TypeScript strict mode
- **Production**: Docker support, PM2 ready, cloud deployment guides

### Contact Information
For support, questions, or collaboration opportunities:
- Create an issue in this repository
- Contact the development team
- Join our community discussions

---

**Built with ❤️ for the entrepreneurial ecosystem**

*CITBIF - Empowering Innovation, Fostering Growth*
