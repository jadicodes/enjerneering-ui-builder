# User
***No end user runnable environment without the .env file exists as of now, so this guide will assume node.js and a working .env file are present.***
***This document also assumes that the user has both projects cloned from GitHub, as there is no current external environment for both projects.***
## Step 1: Run the Local Environments for Each Project 
### Main: ***Enjerneering UI Builder***
![image](https://github.com/user-attachments/assets/ac468ae7-1769-4925-9f99-0bbc38b84517)
- With node.js installed and the .env using the 'npm run dev' command in the VSCode terminal will give you a localhost:3000 link which you can control click to be taken to a test/dev environment of the site
  - within the .env, add NEXT_PUBLIC_WEB_VIEWER="https://enjerneering-web-viewer.vercel.app/" to the end of the file
- This site will allow you to explore the main site of the project
### Secondary: ***Web Viewer Project***
- The Web Viewer is Now Hosted within Vercel and does not require user setup

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
### Global Navbar
![image](https://github.com/user-attachments/assets/57f4a76b-01ac-460a-99fe-7482530d8096)
### Global Footer
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
![image](https://github.com/user-attachments/assets/9545f529-d9d4-4cd0-8e59-219ab269d403)
### Enjoy Making Fun Buttons
![image](https://github.com/user-attachments/assets/2bfa8256-f263-4e36-b1c4-7ece956e2509)
### You can also make as many Pages as you'd like! 
![image](https://github.com/user-attachments/assets/ab7fc0ea-2b62-4136-9da3-0122ab65a358)


## Step 10A: Save and View the Webpage
### Click this Button at the top of the Builder page
![image](https://github.com/user-attachments/assets/43f4e0e4-1528-46e2-8d5c-ee684871b042)
- This button will save the data from your builder within the database and pull that data into the WebInfoViewer project to display a preview of your page, which you will be redirected to in another tab
### View Your Webpage 
![image](https://github.com/user-attachments/assets/2352a400-bb57-40d5-ad54-1a05d8085b6c)
- The preview of your webpage will be shown in the Web Viewer's Vercel Page
  - Currently, the Footer and Textbox within the Global Configurations, and the Hero Header, Main Content, Contact, and Call To Action Sections within the pages section. All of these will be shown as intended and as designed in the builder.
### Explore Your Pages
![image](https://github.com/user-attachments/assets/c2998f50-40ed-4335-bfb0-822b15f677c1)
- Using the footer, or buttons with internal pathing, for navigation, you can explore the pages that you created

## Step 10B: Publish To GitHub
### Clicking the 'Publish Site' Button
![image](https://github.com/user-attachments/assets/b6207f4c-7a81-4c88-98cd-d2ac3bdfaf49)
- This will give you the option to publish your creation into a GitHub repository by clicking the "Publish to GitHub" button
- This will ask you to accept a GitHub App, which will create the repository for you
![image](https://github.com/user-attachments/assets/15f15415-2dec-45fb-87f6-cf87180aaedc)
- The repository will be named after your project's name
- You can use this repository to host your website, I chose to use Vercel
![image](https://github.com/user-attachments/assets/1430c627-97c0-4f3d-8b69-8ac89d5e3319)
- With this, you are able to host a website using the Github Repo with every aspect being fully functional!! 



### **With that, you have successfully Created a Project, Built a Page in the Builder, and Created a Real Website with It!**
