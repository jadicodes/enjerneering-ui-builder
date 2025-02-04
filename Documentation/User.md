# User
***No end user runnable environment without the .env file exists as of now, so this guide will assume node.js and a working .env file are present.***
***This document also assumes that the user has both projects cloned from GitHub, as there is no current external environment for both projects.***
## Step 1: Run the Local Environments for Each Project 
### Main: ***Enjerneering UI Builder***
![image](https://github.com/user-attachments/assets/ac468ae7-1769-4925-9f99-0bbc38b84517)
- With node.js installed and the .env using the 'npm run dev' command in the VSCode terminal will give you a localhost:3000 link which you can control click to be taken to a test/dev environment of the site
- This site will allow you to explore the main site of the project
### Secondary: ***WebInfoViewer Project***
![image](https://github.com/user-attachments/assets/3aa9a2c9-bb2c-4205-85d2-425e2e9483e1)
- With node.js installed, use the 'npm run viewer' command within the VSCode terminal to begin running the localhost:3000 server, which will later be used by the main Enjerneering project
- This site can be used manually, but it will be used as a redirect from the main project, so there's no need to control click into it 

## Step 2: Explore the Workspace Page
![image](https://github.com/user-attachments/assets/ff0bdc5e-138e-41ef-b818-51f8864d8358)
- When you control click into the localhost:3000, you will be taken to a login page for clerk auth, which will then redirect you to this page. This is the workspace page, which is the main dashboard of the projects a user may have
- This screen will have no projects unless the user has already made a project that has been saved to the database
  - Using the triple dot on the bottom right of a project's card, you will be given 3 options edit details, preview, and delete website, all of which are working
- One the left side of the screen, 'Deleted Files' will take you to a page that would hold the deleted project files and 'Settings' will take you to a page that allows you to see your account details
- The yellow 'Create New Website' Button in the top right of the screen will take you to the next step in the process

## Step 3: Creating a Website Project - *Part 1: Getting Started*
![image](https://github.com/user-attachments/assets/319fb785-b330-4d99-a9fd-77d09ab038f6)
- After being taken to the 'Create Website' Page, you have the option to fetch information from an existing website. If a url is entered and the 'Fetch Data' button is clicked, the next information form will be filled with mock website info.
- If the 'Continue without Existing Website' button is clicked, you will be taken to the next information form with blank fields.

## Step 4: Creating a Website Project - *Part 2: Project Initialization*
![image](https://github.com/user-attachments/assets/40340bb0-b2a6-4160-ad69-d1cd2311b271)
- After continuing from the last page, you will be taken to this page, where you will fill in all of the fields on this page to initialize the project's information. The screenshot shows a filled in form with the mock project information (the 'Fetch Data' option).
- Once the information and Photos have been inputted, you will press continue and be taken to the services page

## Step 4.5: Creating a Website Project - *Part 2.5: Adding Services*
![image](https://github.com/user-attachments/assets/b4d5a4cf-53f4-4f7c-863d-32de8b36096b)
- After continuing from the Project Initialization page, you will be taken to the 'Add Services' page, which is an optional page which can be skipped using the 'Skip for now' Button.
- If you decide not to skip this and want to add services, you can press the 'Add Service' Button in the middle of the screen, which will present you a popup screen, as seen below:
![image](https://github.com/user-attachments/assets/877bd945-08be-49e7-b873-769d382e4237)
- In this window, you can fill in the information fields that correspond to the service you'd like to add (or fill them in with mock info), then click the 'Add Service' button in the bottom right of the window

## Step 5: Creating a Website Project - *Part 3: Website Information*
![image](https://github.com/user-attachments/assets/1b552951-de2f-4916-a83a-067811e21fd5)
- After continuing through the 'Services' page, you will be taken to the final page of the project creation process. One this page, you will input the Name, URL, and Icon for your website.
- Once these pieces of information have been inputted into their corresponding fields, you can click the 'Continue' button in the bottom right of the screen, which will create the project and redirect you to the builder page

## Step 6: Checking on Your Created Project
![image](https://github.com/user-attachments/assets/82385d32-d16b-4144-bb8e-0a5cd9544575)
- Once you have continued from the Website Information page, your project will be sent to the database and you will be redirected to the builder page, as shown in the screenshot.
- This page is currently limited. You can add many things, but only some will be sent to the preview screen

## Step 7: Add Your Webpage Elements
![image](https://github.com/user-attachments/assets/98c9c1b8-cd7e-41e1-b448-c4a2d991ef04)
- Elements from the left sidebar can be added by clicking through their menus.
- The elements will be added to your builder screen in the middle 

## Step 8: Make it Your Own! - *Part 1: Global Configurations*
![image](https://github.com/user-attachments/assets/d872a2fe-c030-405c-9b52-7250e7cb3ff2)
- Using the right side bar, between the 'Variants' and 'Change Content' tabs, you will be able to make your elements your own with your logo and whatever you'd like for text, links, etc.
- Some formatting (spacing within elements, element spacing on the page, etc.) is still being worked on and will be improved in the future

## Step 9: Make it Your Own! - *Part 2: Sections*
### By clicking a page on the left sidebar
![image](https://github.com/user-attachments/assets/c2fda18f-0cd2-4c9e-b0e2-18ecc282c23b)
### You will be given the option to add a New Section
![image](https://github.com/user-attachments/assets/5fec4814-3983-4b24-809c-f676e8d6689f)
### Then you can choose the Section you want
![image](https://github.com/user-attachments/assets/2c6f1863-f673-4a5d-a880-70bfceb62ca6)
### You can then design your Section to your heart's content!
![image](https://github.com/user-attachments/assets/e7c09d67-c861-4348-999b-8a15f18010e2)
- For this example, I chose to use the header along with the footer of the global components
  - The Hero Header, Main Content, Contact, and Call To Action sections are all working
  - Currently, only the first style of each component is fully working, with more to come. 

## Step 10: Save and View the Webpage
### Click this Button at the top of the Builder page
![image](https://github.com/user-attachments/assets/409c97b8-a97e-4538-ba29-e664f4e31a6a)
- This button will save the data from your builder within the database and pull that data into the WebInfoViewer project to display a preview of your page, which you will be redirected to in another tab
### View Your Webpage 
![image](https://github.com/user-attachments/assets/c71ec8ba-81e5-4ec1-9bfc-7e4da960c11a)
- The preview of your webpage will be shown in the localhost:4000 server from the WebInfoViewer
  - Currently, the Footer and Textbox within the Global Configurations, and the Hero Header, Main Content, Contact, and Call To Action Sections within the pages section. All of these will be shown as intended and as designed in the builder.
  - Some of the styling changes a bit when going to the preview, since the relative sizing is different when transferred to the full screen preview
- The 'Back to Main Page' button at the bottom will take you to main page of the WebInfoViewer, which will allow you to check other information that corresponds to the project you created. 

### Example of Multiple Sections being shown in order
![image](https://github.com/user-attachments/assets/c0655ca5-3fb4-4f33-96d3-80795808c47a)
*The Sections are Weird looking because the CSS in the tailwind for enjerneering isn't made for a full screen webpage, but for the builder preview. This will be fixed in the next iteration*


### **With that, you have successfully Created a Project, Built a Page in the Builder, and Created a Preview of the Webpage!**
