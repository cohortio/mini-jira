# Mini-Jira

## Overview
Team Task & Issue Tracker (Mini-Jira)
A small but realistic app where users can:

- Sign up / log in
- Create projects
- Create & assign tasks/issues to people
- Comment on tasks
- Track status (To do / In progress / Done)
- See dashboards and filters

## Technologies 

### Frontend (React)
- React components, props, and state
- Forms (validation, error handling, controlled inputs)
- React Router (routing, protected routes)
- API calls (fetch/axios, handling loading/error states)/GraphQL(future)
- State management (local state + maybe Context or a simple global store)
- Basic UI patterns: tables, modals, toasts, pagination, search/filter UI

### Backend
- REST API design (resources like /projects, /issues, /comments, /users)
- CRUD operations and request validation
- Auth with JWT or sessions (login, signup, password hashing)
- Role-based access (e.g., only project owners can edit project settings)
- Database modeling (users, projects, issues, comments, etc.)
- Error handling and logging

### DevOps / “Real world” bits
- Environment variables (dev vs prod)
- Connecting to a cloud database (e.g., hosted Postgres)
- Deployment (frontend + backend)
- Basic security concerns (password hashing, CORS, not exposing secrets)
- CI/CD pipelines

### Suggested Tech Stack

#### Frontend

- React (possibly with TypeScript)
- React Router
- CSS framework: Tailwind or plain CSS/SCSS (Tailwind speeds things up)
- Data fetching: fetch/axios or TanStack Query (as a later enhancement)

#### Backend
- Node.js + Express ([NestJs](https://nestjs.com/))
- PostgreSQL (via Prisma or Sequelize, or plain SQL with a query builder like Knex)
- JSON Web Tokens (JWT) for auth
- Zod / Joi / Yup for input validation (optional but very educational)

## Core Features (MVP)

These are the must-haves that already teach a lot:

- User Accounts
   - Sign up with email + password
   - Log in / log out
   - Persist login with a token in localStorage or cookies
   - “My Profile” page with basic info

- Projects
   - Create a project (name, description)
   - List of all projects the user is a member of
   - View a single project page

- Issues / Tasks
   - Each project has issues:
      - title
      - description
      - status (todo, in-progress, done)
      - priority (low/medium/high)
      - assignee (optional)

   - On the frontend:
      - List of issues for a project
      - Create / edit / delete issue
      - Filter by status / assignee / text search
- Comments
   - Each issue has a comment thread
   - Create comment, display them ordered by time
   - Show author & timestamp
- Basic Auth Protection
   - Only logged-in users can see projects and issues
   - Only project members can see a given project
   - Simple roles: owner vs member (e.g., only owner can delete project)