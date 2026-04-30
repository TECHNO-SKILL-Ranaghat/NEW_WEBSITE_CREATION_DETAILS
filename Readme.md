# NEW_WEBSITE_CREATION_DETAILS

## Project Overview

This project is a modular education management platform with separate frontend and backend services. It supports visitor interactions, student portals, franchise portals, and admin dashboards for managing courses, admissions, payments, exams, notifications, and media.

The architecture is designed for scalability with Node.js, Express.js, MongoDB, and a modern React/Next.js frontend.

## Core Features

- Role-based user access: admin, student, Franchise
- Authentication: JWT, refresh tokens, Google OAuth
- Student admissions, registration, and course management
- Franchise application workflow and approval process
- Wallet management with transaction history
- Payment integration and webhook handling
- Assessments: exams, exam attempts, results, certificates
- Content management: popups, banners, gallery, licenses
- Notifications and alert system
- Analytics dashboards for admin insights

## Tech Stack

- Frontend: React.js / Next.js
- UI: Tailwind CSS, ShadCN UI, Lucide icons
- Backend: Node.js, Express.js
- Database: MongoDB with Mongoose
- Authentication: JWT + Refresh Tokens, Google sign-in
- Validation: Joi or Zod
- Payments: Razorpay
- Storage: Cloudinary / AWS S3
- Caching / sessions: Redis
- Logging: Winston / Pino
- Testing: Jest, Supertest, React Testing Library

## Architecture and Folder Structure

Expected workspace layout:


##### Client
   *public*
   *src*
   *components*
   *pages*
   *hooks*
   *redux*
   *utils*

##### Server
   *controllers*
   *routes*
   *services*
   *models*
   *validations*
   *config*
   *middleware*
   *server.js*
   *app.js*


### *API Overview*

Base path: /api/v1

### Auth

- POST /auth/register
- POST /auth/login
- POST /auth/refresh-token
- POST /auth/logout
- GET /auth/google

### User

- GET /users/me
- PATCH /users/me
- GET /users/:id

### Student

- GET /students
- POST /students
- GET /students/:id
- PATCH /students/:id
- DELETE /students/:id

### Franchise

- POST /franchises/apply
- GET /franchises
- GET /franchises/:id
- PATCH /franchises/:id

### Wallet

- GET /wallets/:franchiseId
- POST /wallets/transactions
- GET /wallets/transactions

### Course

- GET /courses
- POST /courses
- PATCH /courses/:id
- DELETE /courses/:id

### Admission

- POST /admissions
- GET /admissions
- PATCH /admissions/:id

### Payment

- POST /payments
- GET /payments/:id
- POST /payments/webhook

### Exam

- POST /exams
- GET /exams

### Exam Attempts

- POST /exam-attempts
- PATCH /exam-attempts/:id
- GET /exam-attempts/:studentId

### Result

- GET /results/:studentId

### Notification

- GET /notifications
- PATCH /notifications/:id
- POST /notifications

### Popup

- GET /popups
- POST /popups
- PATCH /popups/:id
- DELETE /popups/:id

### Banner

- GET /banners
- POST /banners
- PATCH /banners/:id
- DELETE /banners/:id

### License

- GET /licenses
- POST /licenses
- DELETE /licenses/:id

### Analytics (Admin)

- GET /analytics/dashboard
- GET /analytics/revenue
- GET /analytics/students

## Database Schemas Summary

Key collections and models expected:

- User: auth, roles, refresh tokens, profile data
- Student: registration, franchise, documents
- Franchise: institute data, status, franchise code
- Wallet: franchise balances, main and SRB wallets
- Transaction: wallet credits, debits, references
- Course: course structure, fees, semesters, subjects
- Admission: student admission requests and approvals
- Payment: payment tracking, Razorpay details
- Exam: exam definitions
- Question: exam questions and options
- ExamAttempt: student exam submissions
- Result: evaluated exam results and certificates
- Notification: user notifications
- Gallery: media assets
- Popup: active popups
- Banner: homepage banners
- License: license documents

## User Flows

### Visitor Flow

- Browse courses, study centers, gallery, popups, license information
- Submit admission inquiries or franchise applications

### Student Portal

- Secure login and dashboard
- View course progress, exams, fees, certificates, notifications
- Attend exams and access results

### Franchise Portal

- Franchise login and dashboard
- Manage students, admissions, wallet requests, payments, exam requests
- Track pending approvals and franchise status

### Admin Portal

- Admin login and dashboard
- CRUD operations: popups, gallery, courses, licenses
- Approve/reject franchise and admission requests
- Wallet approvals, exam management, analytics, notifications

## Setup Instructions

1. Push or Clone the repository.
   -  https://github.com/TECHNO-SKILL-Ranaghat/AIYCEC_OFFICIAL
      *push code everyday*
2. Install dependencies separately for client and server:
   - cd client && npm install
   - cd server && npm install
3. Configure environment variables for backend:
   - MONGODB_URI
   - JWT_SECRET
   - JWT_REFRESH_SECRET
   - RAZORPAY_KEY_ID
   - RAZORPAY_KEY_SECRET
   - CLOUDINARY_URL or AWS credentials
   - REDIS_URL
   - EMAIL_HOST, EMAIL_USER, EMAIL_PASS
4. Run backend server:
   - cd server && npm run dev
5. Run frontend app:
   - cd client && npm run dev

## Testing

- Backend tests: 
npm test or 
npm run test from server
- Frontend tests: 
npm test from client
- Use Jest, Supertest, and React Testing Library for coverage targets

## Notes

- Use role-based middleware to secure admin, student, and franchise routes.
- Implement input validation with Joi or Zod for all API endpoints.
- Use secure password hashing with bcrypt.
- Add proper error handling and centralized middleware.
- Document APIs with Swagger or Postman.

## Contact

For implementation details or enhancements, inspect project files under server/ and client/, and follow the defined folder structure.
