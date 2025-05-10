# event-management-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```
COS30043-Interface Design and Development

Overview
The purpose of this assignment is to develop a responsive web application using Vue.js 3 and
Bootstrap that allows users to search for events and provides a registration form. The web app
must be deployed to the university web server (Mercury).
Website Requirements
You are required to implement a web application that consists of the following three sections. A
sample screenshot is provided below, which primarily illustrates the three sections to give you an
overall understanding of the website. Please use your own design while ensuring that all
requirements are met.
1. Responsive Content
The web app must include:
• A website title at the top.
• An image related to event management.
• A "Why Choose Us?" section containing six small items, each with:
o A title
o A short description
o You can also include an icon if you like
Interface Design and Development Assignment 1
2
The layout must be implemented using the Bootstrap grid system with three breakpoints:
• Small screens (mobile) → Display items in a single column.
• Medium screens (tablet) → Display items in two columns.
• Large screens (desktop) → Display items in three columns.
2. Event Information (Searchable Table)
• Initially, display all events from events.txt in a table.
• The table must include four columns:
o Event ID
o Event Name
o Category
o Duration Hours
o
Filtering Options:
• Different text inputs for searching by Event ID, Event Name, and Duration.
• Radio buttons for filtering by Category (Technology, Business, Marketing, Finance, All).
3. Registration Form
Implement a registration form that includes:
• A username input field.
• A password input field.
• A confirmation password input field (a message will appear beside the input box if the
passwords do not match).
• Radio buttons to select an event category (default: Business when the web app loads).
• A drop-down list for event names, populated dynamically based on the selected category.
Once the user makes a selection, display a summary message showing:
• Username
• Selected category
• Selected event name
.
Folder Structure
Create a local framework folder with the following subfolders:
css → Store Bootstrap styles
js → Store Bootstrap JavaScript components and vue.global.js
In this assignment, you developed a web application and want to keep all resources under
your web server. This ensures stability and control, preventing unexpected behavior due to
external framework updates.
Interface Design and Development Assignment 1
3
Your folder structure should look like this:
│── framework/
│ ├── css/
│ ├── js/
│── A1/
│── A2/
If you use other tools (like Vue CLI) to create your project, you don’t have to follow this folder
structure.

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
