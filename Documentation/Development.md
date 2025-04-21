Deployment and Maintenance Documentation
This document is meant to serve as a guide on how to deploy, start, stop, and troubleshoot a running system for the enJerneering UI Builder suite of projects.

This system is made up of three separate repositories:
1. **enJerneering UI Builder** – The main platform where users create projects.
2. **enJerneering UI Viewer** – A Supabase-connected viewer for rendering live project data.
3. **enJerneering UI Publisher** – A standalone version of the viewer that runs off a generated `data.json` file for GitHub deployment.

All three systems share a common component set called "web components" or "section types." When updates are made to the builder or viewers, all projects must be kept in sync to prevent rendering or compatibility issues.

---

# Setting Up the Development Environment
To set up the development environment, you will need the source code. That can be found [here](https://github.com/enJerneering/enJerneering-ui-builder). You also will need the [enJerneering UI Viewer](https://github.com/PiersonSilver/WebInfoViewerCapstone) and the [enJerneering UI Publisher](https://github.com/jamaki604/landing-page) repository. For details on the viewer’s structure, refer to the [User Manual](https://github.com/jadicodes/enjerneering-ui-builder/blob/master/Documentation/User.md).

---
# Replicating via Docker

## Getting Started with Docker

### Prerequisites
- Docker installed on your system:
  - [Download Docker Desktop](https://www.docker.com/products/docker-desktop)
  - Linux:
    ```bash
    sudo apt-get update
    sudo apt-get install -y docker.io
    ```
  - Verify installation:
    ```bash
    docker --version
    ```

## Steps to Run the Application with Docker

### 1. Clone the Repository
```bash
git clone https://github.com/enJerneering/enJerneering-ui-builder.git
cd enJerneering-ui-builder
```

### 2. Request and Set Up the `.env` File
- Request the `.env` file from Jerrod at enJerneering.
- Place the `.env` file in the project root.

### 3. Build the Docker Image
```bash
docker build -t enjerneering_ui_kit .
```

### 4. Run the Docker Container
```bash
docker run --env-file .env -p 3000:3000 enjerneering_ui_kit
```

### 5. Access the Application
Visit [http://localhost:3000](http://localhost:3000).

### 6. Stop the Docker Container
Press `CTRL+C` to stop foreground processes or:
```bash
docker ps
docker stop <container_id>
```

---
# Manual Environment Setup

## Required Technologies
- Node.js and npm (latest version)
- Visual Studio Code
- Vitest (used across all three projects for testing)

# Main: ***enJerneering UI Builder***

### Folder Structure
- **app/** – Next.js application pages (organized by route)
- **public/** – Static assets like icons, images, etc.
- **src/** – Shared components, helpers, and utilities
- **supabase/** – Configuration and helpers for interacting with Supabase

### Important Files
- `.env` – Holds environment variables for Supabase, Clerk, GitHub
- `package.json` – Lists dependencies and scripts

### How to Test
```bash
npm install
npm run dev
npm run test
```
Vitest is used for unit testing.

---
# Secondary: ***enJerneering UI Viewer***

### Folder Structure
- **app/** – Viewer routing and components
- **_sections/** – Contains all reusable sections and element definitions

### Testing
```bash
npm install
npm run dev
npm run test
```
Vitest is used for component testing and snapshot validation.
- Navigate to `/debug` and input a project ID from Supabase to test viewer rendering
- For test coverage: `npm run test:coverage`

### Note
- This project connects directly to Supabase.
- It reflects **live** changes made in the UI Builder.

---
# Third: ***enJerneering UI Publisher***

### Overview
The enJerneering UI Publisher is a modified viewer that reads from a static `data.json` file placed inside the `/public` directory. It does **not** connect to Supabase.

### Folder Structure
- **public/data.json** – Required. Must contain valid exported project data.
- **app/** – Page and layout rendering from static data
- **_sections/** – Shared component library (must match UI Builder/Viewer)

### How to Run Locally
```bash
git clone https://github.com/jamaki604/landing-page.git
cd landing-page
npm install
npm run dev
npm run test
```
Vitest is used to ensure all core rendering logic remains valid.

Ensure `public/data.json` exists, and the app will auto-load and display the static project.

### Deployment
- Can be deployed using GitHub Pages, Vercel, Netlify, or any static host
- Ideal for creating permanent, snapshot-based published projects

---
# Shared Component Requirements
Changes to **web components** (`_sections/`) must be synced across:
- UI Builder
- UI Viewer
- UI Publisher

Any updates to Supabase structure or `data.json` formatting require updates to the Viewer and Publisher to ensure consistent interpretation and rendering.

---
This document ensures that developers understand how to set up, run, and maintain each of the three components of the enJerneering platform.
