Deployment and Maintenance Documentation
This document is meant to serve as a guide on how to deploy, start, stop, and troubleshoot a running system for the enJerneering UI Builder, which includes Vercel, Prisma ORM, Supabase, React, Node.js, Clerk Auth, and PostgreSQL.

This project is currently split over three repositories:
1. The main UI Builder system where users create projects.
2. The Web Info Viewer which renders those projects dynamically using Supabase.
3. The GitHub-published Viewer fork, which is a standalone, static viewer of projects based on a generated `data.json` file.

Each is needed to support the full user experience.

For using the UI Builder and Web Info Viewer together, see the User Manual.

### 1. Overview of the Deployment Environment
This project is deployed as a serverless web application, utilizing:
- **Vercel** for hosting both the front end and serverless backend functions.
- **Supabase** for managing the PostgreSQL database.
- **Clerk Auth** for handling user authentication.

This configuration provides a scalable, low-maintenance environment, eliminating the need for traditional servers.

#### Required Services
To deploy and maintain this system, the following accounts and configurations are required:
- **Vercel account** for hosting.
- **Supabase account** with a PostgreSQL database configured.
- **Clerk Auth account** for user authentication.

Additional tools for local development and testing include:
- **Node.js** for running the application locally.
- **Prisma CLI** for managing database schema.

### 2. Server Requirements
This is a serverless application hosted on Vercel:
- **Vercel** handles front-end and backend logic via serverless functions.
- **Supabase** provides the managed PostgreSQL database.
- **Clerk** provides authentication and user session management.

### 3. Project Structure and File Placement
This section explains where each folder and file should go and what each component is for:

#### Main Project Folders
- **app/**: Main application files (React components and pages).
- **.storybook/**: Local development UI testing with Storybook (not deployed).
- **api/**: Serverless functions. Automatically deployed by Vercel.
- **prisma/**: Contains Prisma schema files. Used for local database syncing.
- **node_modules/**: Installed dependencies. Vercel installs these at runtime.
- **log/**: Local development logs. Not deployed.
- **supabase/**: Supabase configuration and setup (not deployed).
- **public/**: Static assets like logos and images. Deployed.
- **src/**: Source code including utilities and components. Deployed.
- **.next/**: Build output. Managed by Vercel.

#### Root Files
- **.env**: Critical environment variables. Set in Vercel dashboard.
- **next.config.js, tailwind.config.ts, tsconfig.json**: Configuration for build tools. Required.
- **README.md, LICENSE**: Documentation and licensing. Optional but recommended.

### 4. Starting and Stopping the System
#### Start the System
- Push to GitHub or trigger a manual build in the Vercel dashboard.
- Supabase and Clerk run continuously.
- For local testing:
  - Run `npm install`
  - Run `npm run dev`

#### Stop the System
- No action needed for production (serverless).
- Stop local development with `Ctrl+C` in the terminal.

### 5. Troubleshooting Common Issues
- **Vercel Logs**: For errors in serverless functions.
- **Supabase Logs**: For database query or function issues.
- **Clerk Logs**: For authentication problems.

#### Common Issues
- Missing environment variables.
- Database connection failures.
- Incorrect Clerk Auth setup.

### 6. Critical Points and Potential Failures
- Environment variables must be set correctly.
- Supabase access must remain active.
- Clerk must be properly configured for authentication.

#### Preventive Measures
- Back up Supabase regularly.
- Monitor all third-party dashboards for limits and errors.

### 7. Testing the System
- Deploy and confirm status in Vercel.
- Verify Supabase DB queries.
- Test Clerk user auth with a test user.
- Check GitHub publish flow (see below).

### 8. Publishing to GitHub as a Static Viewer
A new publishing flow has been added to the main UI Builder app. When the user presses **Publish**, the following steps occur:

1. The current project is saved to Supabase.
2. A JSON object (`data.json`) is generated from Supabase.
3. The project repository is created under the user’s GitHub account from a template (`enJerneering-web-publisher`).
4. The generated `data.json` is uploaded to `/public/data.json` in the repo.

This enables the **static viewer repository** (a fork of the original viewer) to load the project from `public/data.json` without needing Supabase access.

#### Requirements
- The user must have authenticated GitHub via the GitHub App.
- The GitHub App must be installed for the user.
- The user must have public repo creation permissions.

#### How to Deploy Manually to Live Hosting
If not using Vercel:
- Clone the GitHub repo created from the publish step.
- Use GitHub Pages, Vercel or Netlify to deploy the static repo.
- Ensure `/public/data.json` is correctly committed.

---

This static GitHub-published version acts as a **snapshot** of the project at the time of publishing. For dynamic updates, the Supabase-connected viewer should be used.

### Summary
The UI Builder uses Vercel + Supabase + Clerk for real-time editing and dynamic previewing. The static GitHub export provides a lightweight, hostable alternative that does not depend on Supabase or Clerk once deployed.
