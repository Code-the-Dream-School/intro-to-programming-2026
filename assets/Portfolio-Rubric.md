# Portfolio Project Rubric

## General
- [ ] Project is published on a public GitHub repository
- [ ] Code executes without errors in the browser

## Project Structure
 - [ ] README.md (_NOTE:_ this file is typically used to explain how someone can run your code, but it does not need to contain this content for your final project to be acceptable)
 - [ ] index.html
 - [ ] css folder
   - [ ] index.css
 - [ ] js folder
   - [ ] index.js 
 - [ ] (OPTIONAL) images folder

## index.html
 - [ ] Include proper boilerplate code
 - [ ] (OPTIONAL) Use a font-family or Google fonts
 - [ ] index.css and index.js file should be properly linked to this file
 - [ ] Level 1 heading with student's name
 - [ ] Navigation with working internal links to the following sections:
    - [ ] About
    - [ ] Experience
    - [ ] Skills
    - [ ] Projects
    - [ ] Leave a Message
    - [ ] Open API Page
    - [ ] (OPTIONAL) Connect or Contact Me section to contain email and social media links
 - [ ] (OPTIONAL) Sticky/fixed navigation that stays in place when user scrolls down on the page
 - [ ] (OPTIONAL) Dark mode toggle switch to change coloring of background and text between default and dark mode
 - [ ] (OPTIONAL) Navigation converted to a hamburger menu on smaller devices via media queries

## About Section
 - [ ] Level 2 heading
 - [ ] One or more paragraphs of text
 - [ ] (OPTIONAL) Your photo with alt attribute for accessibility 

## Experience Section
 - [ ] Level 2 heading
 - [ ] List of previous work or experience or one or more paragraphs of related experiences if student has no previous work experience)
 - [ ] If listing experience, this should be styled in grid or flexbox layout

## Skills Section
 - [ ] Level 2 heading
 - [ ] List of skills, inserted using JavaScript from the index.js file
 - [ ] List should be styled in a grid or flexbox layout

## Projects Section
 - [ ] Level 2 heading
 - [ ] List of GitHub repositories, fetched using the GitHub API and inserted using JavaScript from the index.js file 
 - [ ] (OPTIONAL) Each GitHub repository name is a clickable link that takes the user to that repository
 - [ ] (OPTIONAL) Display additional information about each of the repositories (examples: created date, description, etc.)
 - [ ] (OPTIONAL) Customize the styling of your projects list (cards or use of flexbox or grid for examples)

## Leave a Message Section (Form and Messages List)
 - [ ] Level 2 heading for form
    - [ ] Name, Email Address, and Message fields
    - [ ] Submit button
    - [ ] Event listener that adds the form field inputs to the messages section
 - [ ] Level 2 heading for messages
    - [ ] List of messages (once the form has been given inputs and submit button clicked) styled in a grid of flexbox layout
      - [ ] Each message item should have the following:
        - [ ] Name of message author as a clickable link to email the author at the email address they provided in the form
        - [ ] Message text
        - [ ] Remove button to delete the message from the list of messages
        - [ ] (OPTIONAL) Edit button for user to change one (or more) of the form inputs (name, email, message)
    - [ ] (OPTIONAL) conditionally render (meaning hide/display) the level 2 heading and section content depending on whether or not there are messages

## (OPTIONAL) Connect or Contact Me
_NOTE:_ If you do not have a Connect or Contact Me section, your links should be in the footer of your page as icons/images
 - [ ] Clickable link to email the student 
 - [ ] At least two social media links to the student's profile pages (examples: GitHub, LinkedIn, twitter, instagram, etc.)
 - [ ] (OPTIONAL) Use icons or images in place of text string links for your email and 2+ social media links

## Footer
 - [ ] Copyright logo, current year, and student's name inserted using JavaScript from the index.js file
 - [ ] Email and 2+ social media icon/image links (if the page does NOT have a Connect or Contact Me section)

## index.js
 - [ ] Comments in code as appropriate (to notate what sections of code are used for)
 - [ ] Sections of code to accomplish the following:
   - [ ] Insert the copyright logo, current year, and student's name in the footer of index.html
   - [ ] Using an array, insert the array items as a list of skills in the skills section of index.html
   - [ ] Handle the event listener on the message form to insert the following into the messages section:
     - [ ] Convert form inputs into the author's name as a clickable link 
     - [ ] Display their message and 
     - [ ] Provide a remove button to delete the message
     - [ ] (OPTIONAL) Provide an edit button to change one or more form fields
     - [ ] (OPTIONAL) Conditionally render the messages header and section of index.html (show it if there are messages, hide it if none)
   - [ ] Using API fetch, insert the names of your GitHub repositories in the projects section of index.html
     - [ ] (OPTIONAL) Provide additional information about each repository
     - [ ] (OPTIONAL) Make the repository names clickable links that redirect the user to that repository page

## index.css
 - [ ] Comments in code as appropriate (to notate what sections of code are for)
 - [ ] Flexbox (or Grid) used to format the layout of the Experience and Connect sections _(NOTE: If you are using social media icons in your footer in place of a Connect section, you should use Flexbox or Grid to format the layout of your icons in the footer)_

## (OPTIONAL) images folder
 - [ ] If you've elected to use images in your portfolio, be sure to have an images folder at the root level of your repository (same level as your index.html and README.md files).  All your images should go in this folder
 - [ ] Make sure images used in your html or css files are properly linked to the image inside your images folder
 - [ ] Remember to use alt for any images so there will be helper text if the image is not displayed properly

## Styling
Everyone's style is different and we encourage students to let the style of their site represent them.  That being said, there are some general style guidelines we encourage you to follow:
 - [ ] Styling is effective (example: font-sizes are not too small or large, colors are not too dark/light to be easily seen, etc.)
 - [ ] Remember to have appropriate contrast to your site - don't use a dark font on a dark background