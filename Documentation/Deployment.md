# **Deployment and Maintenance Documentation**

This document is meant to serve as a guide on how to deploy, start, stop, and troubleshoot a running system for the enJerneering UI Builder, which includes Vercel, Prisma ORM, Supabase, React, Node.js, Clerk Auth, and PostgreSQL.

This project is currently split over two repositories, the [source code](https://github.com/enJerneering/enJerneering-ui-builder) and the [Web Info Viewer](https://github.com/PiersonSilver/WebInfoViewerCapstone). Both of these are needed to maintain a full user experience. For the specifics on using these together, read the information in the [User Manual](https://github.com/jadicodes/enjerneering-ui-builder/blob/master/Documentation/User.md).

---

## **1. Overview of the Deployment Environment**

This project is deployed as a serverless web application, utilizing:
- **Vercel** for hosting both the front end and serverless backend functions.
- **Supabase** for managing the PostgreSQL database.
- **Clerk Auth** for handling user authentication.

This configuration provides a scalable, low-maintenance environment, eliminating the need for traditional servers.

### **Required Services**
To deploy and maintain this system, the following accounts and configurations are required:
- **Vercel** account for hosting.
- **Supabase** account with a PostgreSQL database configured.
- **Clerk Auth** account for user authentication.

Additional tools for local development and testing include:
- **Node.js** for running the application locally.
- **Prisma CLI** for managing database schema.

---

## **2. Server Requirements**

Since this is a serverless application hosted on Vercel, there is no need for a traditional server. However, ensure the following:

1. **Vercel** handles front-end and serverless function hosting.
2. **Supabase** provides the database (PostgreSQL) as a managed service.
3. **Clerk Auth** is configured for user authentication and authorization.

Vercel’s serverless functions will auto-scale with demand, but be mindful of any rate limits or usage quotas on Vercel, Supabase, and Clerk.

---

## **3. Project Structure and File Placement**

This section explains where each folder and file should go and what each component is for:

### **Main Project Folders**

- **`app/`**: Main application files (React components and pages).  
  **Deployment**: All files in `app/` are automatically deployed to Vercel as part of the front end.

- **`.storybook/`**: Configuration for Storybook, a tool for developing and testing UI components.
  **Deployment**: Only needed for local development, not production.

- **`api/`**: Serverless functions for backend logic.
  **Deployment**: Vercel automatically deploys each file in this folder as an API endpoint.

- **`prisma/`**: Contains Prisma ORM files, including the schema definition for the database.
  **Deployment**: This folder’s contents are not directly deployed but are used to manage the database schema. Run Prisma commands (`prisma migrate` or `prisma generate`) to synchronize this schema with Supabase.

- **`node_modules/`**: Contains installed dependencies.
  **Deployment**: Excluded from deployment, as Vercel installs dependencies automatically during deployment. Only needed for local development.

- **`log/`**: Stores application logs for debugging.
  **Deployment**: Exclude this folder from deployment. It’s used for local development troubleshooting.

- **`supabase/`**: Contains Supabase configurations.
  **Deployment**: Used for database management but not directly deployed. Necessary for setting up or reconfiguring the database with Supabase.

- **`public/`**: Contains static assets like images, icons, and logos.
  **Deployment**: Files in this folder are deployed to Vercel and served as static assets.

- **`src/`**: Main source code for the project, including React components and utilities.
  **Deployment**: Deployed to Vercel along with `app/` since it contains front-end logic.

- **`.next/`**: Contains the build output from Next.js.
  **Deployment**: Generated automatically during deployment. Vercel manages this.

### **Root Files**

- **`.env`**: Stores environment variables like database URLs and API keys. **Critical for functionality**.
  **Deployment**: Do not upload directly. Instead, configure variables in Vercel’s environment settings.

- **`.editorconfig`, `.eslintignore`, `.eslintrc.json`, `.gitignore`, `.prettierignore`, `.prettierrc`**: Config files for code formatting, linting, and version control.
  **Deployment**: Not needed for production, only used in development.

- **`LICENSE`**: Specifies project licensing.
  **Deployment**: Optional, but good to include for open-source projects.

- **`logo.png`**: Used for branding or as a favicon.
  **Deployment**: Place in `public/` to make it accessible as a static asset.

- **`middleware.ts`**: Contains custom middleware for request handling.
  **Deployment**: Deployed to Vercel; essential for handling requests.

- **`next-env.d.ts`**: TypeScript declarations for Next.js.
  **Deployment**: Automatically required, typically not modified manually.

- **`next.config.js`**: Next.js configuration file.
  **Deployment**: Vercel uses this automatically for configuration during deployment.

- **`package-lock.json` and `package.json`**: Define project dependencies and scripts.
  **Deployment**: Vercel uses these to install necessary packages.

- **`postcss.config.js`**: Configuration for PostCSS (e.g., for Tailwind CSS).
  **Deployment**: Required by Vercel if using PostCSS.

- **`README.md`**: Project documentation.
  **Deployment**: Optional, but useful for reference.

- **`tailwind.config.ts`**: Tailwind CSS configuration file.
  **Deployment**: Required if using Tailwind CSS. Vercel references this during build.

- **`tsconfig.json`**: TypeScript configuration file.
  **Deployment**: Needed for TypeScript support.

---

## **4. Starting and Stopping the System**

### **To Start the System**
1. **Deployment on Vercel**: Deployments happen automatically with new commits or can be triggered manually via the Vercel dashboard.
2. **Database with Supabase**: Once configured, Supabase runs continuously without manual intervention.
3. **Local Testing**:
   - Follow along with the Docker instructions found [here](https://github.com/jadicodes/enjerneering-ui-builder/blob/master/Documentation/Development.md).
   - Run `npm install` to install dependencies.
   - Run `npm run dev` to start a local development server for testing.

### **To Stop the System**
- In production, Vercel’s serverless environment does not require manual stopping.
- For local testing, exit the development server by pressing `Ctrl+C` in the terminal.

---

## **5. Troubleshooting Common Issues**

### **Finding Errors**
- **Vercel Logs**: Check the Vercel dashboard under "Logs" for errors from serverless functions.
- **Supabase Logs**: Access the Supabase dashboard to view database or API errors.
- **Clerk Auth Logs**: Clerk provides activity and error logs in its dashboard for user authentication issues.

### **Common Issues and Solutions**
- **Environment Variable Errors**: Ensure all necessary variables (database URL, API keys) are set correctly in Vercel’s environment settings.
- **Database Connection Issues**: Verify the connection string in Supabase and test it using Prisma commands.
- **Authentication Issues**: Confirm that Clerk Auth keys are correctly configured and that permissions are enabled.

---

## **6. Critical Points and Potential Failures**

### **Critical Components**
- **Environment Variables**: Missing or incorrect variables are common failure points.
- **Database Connectivity**: Ensure Supabase PostgreSQL is accessible and online.
- **Authentication**: Any issues with Clerk Auth can prevent user access.

### **Preventive Measures**
- Regularly back up Supabase data.
- Monitor Vercel and Supabase dashboards for any warnings or rate limits.

---

## **7. Testing the System**

To operate the system, verify the following steps:
1. Deploy the project on Vercel and check the deployment status in the dashboard.
2. Confirm database accessibility and functionality in Supabase.
3. Test authentication by creating a test account with Clerk.
4. Check Vercel and Supabase logs for any errors or issues.
