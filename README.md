# SkillBridge Connect

SkillBridge Connect is a college mini project designed to connect customers with skilled local workers such as carpenters, plumbers, electricians, painters, cleaners, drivers, and other service providers.

The platform allows workers to create professional profiles, list their skills and experience, upload certificates, receive booking requests, and communicate with customers. Customers can search for workers, view profiles, make bookings, send messages, and provide ratings or feedback after service completion.

## Project Type

Mini Project - College Academic Project

## Team Members

- Puneeth J
- Raghunandan A S
- Vijay R Gali
- Vikas Sampath

## Key Features

- Customer and worker registration/login
- Worker profile creation with skills, experience, hourly rate, and location
- Search and filter workers by service, location, budget, and rating
- Booking request system for customers and workers
- Booking status management: pending, confirmed, completed, cancelled, and rejected
- Feedback and rating system for completed bookings
- Certificate upload support for workers
- Admin dashboard for analytics, reviews, disputes, and commission details
- Real-time chat support using Socket.IO
- Multi-language preference support
- AI-style assistant search flow for service discovery
- My Bookings and My Services sections for role-based activity tracking

## Tech Stack

### Frontend

- HTML5
- CSS3
- Vanilla JavaScript

### Backend

- Node.js
- Express.js
- Socket.IO
- JWT authentication
- Multer for file uploads

### Database

- MySQL
- SQL schema included in `database.sql`

## Project Structure

```text
SkillBridge-Connect/
├── public/
│   ├── index.html
│   ├── app.js
│   └── style.css
├── uploads/
├── database.sql
├── create_admin_tables.sql
├── reset_database.sql
├── server.js
├── package.json
├── package-lock.json
└── README.md
```

## Prerequisites

Install the following before running the project:

- Node.js
- npm
- MySQL Server

## Installation and Setup

1. Clone the repository:

```bash
git clone https://github.com/vikassampath/SkillBridge-Connect.git
cd SkillBridge-Connect
```

2. Install dependencies:

```bash
npm install
```

3. Create the MySQL database:

```sql
CREATE DATABASE skillbridge;
```

4. Import the database schema:

```bash
mysql -u root -p skillbridge < database.sql
```

5. Create a `.env` file in the project root:

```env
PORT=3000
DB_HOST=127.0.0.1
DB_PORT=3306
DB_USER=root
DB_PASS=your_mysql_password
DB_NAME=skillbridge
JWT_SECRET=replace-with-a-long-random-secret
ADMIN_USERNAME=ATMECE
ADMIN_PASSWORD=change_this_password
ADMIN_EMAIL=admin@example.com
GOOGLE_API_KEY=
```

6. Start the server:

```bash
npm start
```

For development mode:

```bash
npm run dev
```

7. Open the application:

```text
http://localhost:3000
```

If port `3000` is already in use, set another port in `.env`, for example:

```env
PORT=3001
```

## Admin Account

In development, the server creates an admin account from `ADMIN_USERNAME` and `ADMIN_PASSWORD` when the database is available. The local defaults are:

```text
Username: ATMECE
Password: change_this_password
```

Change these values before starting the app. Production does not create an admin account unless both variables are set.

## Important API Modules

- Authentication: `/api/auth/login`, `/api/auth/register`
- Workers: `/api/workers`
- Bookings: `/api/bookings`
- Ratings: `/api/ratings`
- Certificates: `/api/certificates`
- Messages: `/api/messages`
- Admin: `/api/admin/*`
- Semantic search: `/api/semantic-search`

## Notes

- MySQL must be running before using database-related features.
- Uploaded certificates and local runtime files should not be committed.
- Store local secrets only in `.env`; use a unique random `JWT_SECRET` and strong admin password for deployments.
- This project was built as an academic prototype and can be further improved with stronger validation, deployment configuration, and production security practices.

## Future Enhancements

- Improved role-based access control
- Better admin verification workflow
- Payment gateway integration
- Email/SMS notifications
- Advanced worker recommendation system
- Deployment-ready environment configuration

## Acknowledgement

This project was developed as a college mini project to demonstrate a practical web-based solution for connecting skilled workers with customers through a simple digital marketplace.
