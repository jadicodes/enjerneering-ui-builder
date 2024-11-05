# User
***No end user runnable environment without the .env file exists as of now, so this guide will assume node.js and a working .env file are present***
## Step 1: Run the Test/Dev Environment
![image](https://github.com/user-attachments/assets/ac468ae7-1769-4925-9f99-0bbc38b84517)
- With node.js installed and the .env using the 'npm run dev' command in the VSCode terminal will give you a localhost:3000 link which you can control click to be taken to a test/dev environment of the site
- This site will allow you to explore the main feature of iteration 1

## Step 2: Explore the Workspace Page
![image](https://github.com/user-attachments/assets/05578a8a-c74b-4fbb-a94a-3246cbdb361f)
- When you control click into the localhost:3000, you will be taken to a login page for clerk auth, which will then redirect you to this page. This is the workspace page, which is the main dashboard of the projects a user may have
- There are 2 example projects that show what the layout would look like. Using the triple dot on the bottom right of their card, you will be given 3 options (edit details, preview, and delete project), with delete project being the only current working option. This will delete the project from the page and the database
- One the left side of the screen, 'Deleted Files' will take you to a page that would hold the deleted project files and 'Settings' will take you to a page that allows you to see your account details
- The yellow 'Create New Website' Button in the top right of the screen will take you to the next step in the process

## Step 3: Creating a Website Project *Part 1: Getting Started*
![image](https://github.com/user-attachments/assets/319fb785-b330-4d99-a9fd-77d09ab038f6)
- After being taken to the 'Create Website' Page, you have the option to fetch information from an existing website. If a url is entered and the 'Fetch Data' button is clicked, the next information form will be filled with mock website info.
- If the 'Continue without Existing Website' button is clicked, you will be taken to the next information form with blank fields.

## Step 4: Creating a Website Project *Part 2: Project Initialization*
![image](https://github.com/user-attachments/assets/40340bb0-b2a6-4160-ad69-d1cd2311b271)
- After continuing from the last page, you will be taken to this page, where you will fill in all of the fields on this page to initialize the project's information. The screenshot shows a filled in form with the mock project information (the 'Fetch Data' option).
- Once the information and Photos have been inputted, you will press continue and be taken to the services page

## Step 4.5: Creating a Website Project *Part 2.5: Adding Services*
![image](https://github.com/user-attachments/assets/b4d5a4cf-53f4-4f7c-863d-32de8b36096b)
- After continuing from the Project Initialization page, you will be taken to the 'Add Services' page, which is an optional page which can be skipped using the 'Skip for now' Button.
- If you decide not to skip this and want to add services, you can press the 'Add Service' Button in the middle of the screen, which will present you a popup screen, as seen below:
![image](https://github.com/user-attachments/assets/877bd945-08be-49e7-b873-769d382e4237)
- In this window, you can fill in the information fields that correspond to the service you'd like to add (or fill them in with mock info), then click the 'Add Service' button in the bottom right of the window

## Step 5: Creating a Website Project *Part 3: Website Information*
![image](https://github.com/user-attachments/assets/1b552951-de2f-4916-a83a-067811e21fd5)
- After continuing through the 'Services' page, you will be taken to the final page of the project creation process. One this page, you will input the Name, URL, and Icon for your website.
- Once these pieces of information have been inputted into their corresponding fields, you can click the 'Continue' button in the bottom right of the screen, which will create the project and redirect you to the builder page

## Step 6: Checking on Your Created Project
![image](https://github.com/user-attachments/assets/82385d32-d16b-4144-bb8e-0a5cd9544575)
- Once you have continued from the Website Information page, your project will be sent to the database and you will be redirected to the builder page, as shown in the screenshot.
- This page is currently very limited in functionality and will be built up in future iterations.
- You can, however, check on your created project if you return to the 'Workspaces' page, which can be done by clicking the back button to the left of where it says 'UI Builder 2024' in the top left.
![image](https://github.com/user-attachments/assets/ccffeed3-55a8-4123-94e2-a67e5cbdb3fa)
- As you can see, your project that you created will now show in the dashboard, as well as in the database!

### **With that, you have successfully Created a Project and Tested to see that it has been added to both the Dashboard and Database!**
