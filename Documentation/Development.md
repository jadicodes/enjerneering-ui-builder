# Development

## Required Technologies
- Latest versions of [Node.js](https://nodejs.org/en) and npm
- Visual Studio Code IDE

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
    - Install the enJerneering UI Builder via your Git manager.
        This can look like...
        - Copy the repository link (https://github.com/enJerneering/enJerneering-ui.git) to clipboard.
        - Make sure git is installed on your system.
        - Go to the directory you want to clone the repository in.
        - Right click and select "Open Git Bash."
        - Type the command "git clone https://github.com/enJerneering/enJerneering-ui.git".
    - Ensure .env is added to the root of this project.
    - From the terminal, run 'npm i' to install dependencies, then 'npm run dev' to start the server.
