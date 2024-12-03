# Setting Up the Development Environment
To set up the development environment, you will need the source code. That can be found [here](https://github.com/enJerneering/enJerneering-ui-builder), or https://github.com/enJerneering/enJerneering-ui-builder.

# Replicating via Docker

## Getting Started with Docker

This guide walks you through setting up and running the application using Docker.

### Prerequisites

- **Docker**: Make sure Docker is installed on your system.
  - [Download Docker Desktop](https://www.docker.com/products/docker-desktop) for Windows and macOS.
  - For Linux, use your distribution’s package manager:
    ```bash
    sudo apt-get update
    sudo apt-get install -y docker.io
    ```
  - Verify the installation:
    ```bash
    docker --version
    ```

## Steps to Run the Application with Docker

### 1. Clone the Repository

   Clone the project repository from GitHub:
   ```bash
   git clone https://github.com/enJerneering/enJerneering-ui-builder.git
   cd enJerneering-ui-builder
   ```

### 2. Request and Set Up the `.env` File

   - **Request** the `.env` file from Jerrod at enJerneering.
   - Once approved and received, **place the `.env` file in the root directory** of the project.
   - This file contains essential environment variables needed for the application.

### 3. Build the Docker Image

   Build the Docker image from the `Dockerfile`:
   ```bash
   docker build -t enjerneering_ui_kit .
   ```
   - The `-t enjerneering_ui_kit` tags the image with a name, making it easier to refer to later.

### 4. Run the Docker Container

   Start the container, loading environment variables from `.env` and mapping port 3000:
   ```bash
   docker run --env-file .env -p 3000:3000 enjerneering_ui_kit
   ```
   - `--env-file .env` loads environment variables.
   - `-p 3000:3000` maps port 3000 on your local machine to port 3000 in the container.

### 5. Access the Application

   Open a web browser and go to [http://localhost:3000](http://localhost:3000) to view the application.

### 6. Stop the Docker Container

   - To stop the container running in the foreground, press `CTRL+C`.
   - If it’s running in detached mode, list running containers and stop it with:
     ```bash
     docker ps        # Lists running containers
     docker stop <container_id>
     ```
     Replace `<container_id>` with the actual container ID.

### Additional Docker Commands

   - **View Running Containers**:
     ```bash
     docker ps
     ```
   - **View Container Logs**:
     ```bash
     docker logs <container_id>
     ```
   - **Remove a Stopped Container**:
     ```bash
     docker rm <container_id>
     ```
   - **Remove the Docker Image**:
     ```bash
     docker rmi enjerneering_ui_kit
     ```

--- 
# Manual Environment Setup

## Required Technologies
- Latest versions of [Node.js](https://nodejs.org/en) and npm
- Visual Studio Code IDE

# Main: ***Enjerneering Project***

## Folder Structure
### App Folder Holds the Next.js Project is Located
- Each non-hidden (leading underscore) folder within app has a page.tsx file that runs the specific page of the site
    - These will be the main files to update for changing project functionality, as they control the runtime project pages
    - These folders correspond to the actual ../(foldername) page of the site, so the folder structure and site structure are one in the same
- layout.tsx files give the styling for each of the according page.tsx files
- Helper code files or assets files are either within the according folder or are in the public and src folder for when needed

## Important Files
- .env file holds the necessary information for connecting to external services and databases
- package.json holds the dependencies to be installed using npm and the premade scripts to run different testing environments

# How to Test
- Run 'npm run dev' in the VSCode terminal, which will give a localhost link to access a test server of the site
- In this test environment, UI elements can be tested by just clicking through pages
    - Database testing would currently be to manually check that the database information if formatted correctly

## Replicating the Development Environment
  Install the enJerneering UI Builder via your Git manager.
  This is how it looks in Git Bash:
  - Install git to your system.
  - Copy the repository link (https://github.com/enJerneering/enJerneering-ui.git) to clipboard.
  - Make sure git is installed on your system.
  - Go to the directory you want to clone the repository in.
  - Right click and select "Open Git Bash."
  - Type the command "git clone https://github.com/enJerneering/enJerneering-ui.git".
  - Ensure .env is added to the root of this project.
  - From the terminal, run 'npm i' to install dependencies, then 'npm run dev' to start the local server.

# Secondary: ***WebInfoVeiwer Project***

## Folder Structure
### The 'main' Folder holds the Main 'index.js' File which Runs the Express Viewer
- HTML Code strings are stored within public/componentHTML/...
  - content folder has files which hold the code which takes in data from supabase and inputs it into HTML code that can be displayed
  - style folder has files that hold classes that return a string that is used as the CSS for the express output
- Most Code is within those few files, with the additional files/folders being there to allow the app to run as a whole

## Important Files
- The supabase folder holds the supabase URL and Key within the server and client files 
- package.json holds the dependencies to be installed using npm and the premade scripts to run different testing environments

# How to Test
- Run 'npm run viewer' in the VSCode terminal, which will make the localhost link active, so it can be redirected to by the main project
- In this viewer environment, you can either go through the Enjerneering app and be linked to it from the 'Save and View Webpage' Button in builder or use localhost:4000/${projectID} for whatever project you want to test from supabase
    - This testing would be to Manually see that the information is correct for the project details and web elements that were added in builder if you click into the viewer using the 'Go to Viewer' button

## Replicating the Development Environment
  Install the WebInfoViewer Project via your Git manager.
  This is how it looks in Git Bash:
  - Install git to your system.
  - Copy the repository link (https://github.com/PiersonSilver/WebInfoViewerCapstone.git) to clipboard.
  - Go to the directory you want to clone the repository in.
  - Right click and select "Open Git Bash."
  - Type the command "git clone https://github.com/PiersonSilver/WebInfoViewerCapstone.git".
  - From the terminal, run 'npm i' to install dependencies, then 'npm run viewer' to start the local server.
