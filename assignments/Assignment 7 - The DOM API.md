## Get organized and write some code!
- [ ] In your GitHub repository, if you have not yet merged your pull request from last week, merge your open lesson-6 pull request by going to the "Pull Requests" tab of your repository. Click on your open pull request, then click on the green 'Merge Pull Request" and confirm the merge. This will update your main branch with the work you did on your lesson-6 branch.
- [ ] Open your code editor and, in the terminal, make sure you're on your main branch. If you're still on your lesson-6 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-10 work by pulling your changes from your GitHub repository main branch. Use the following git command in your terminal to do this: `git pull origin main`
- [ ] Still in your terminal, create a new local branch to keep track of just the work you'll do for this assignment by running `git checkout -b lesson-7` in the terminal. Doing this also copies the lesson-10 work you merged to main and pulled to your local machine so now all your branches should be identical on your local machine.

## Assignment: Task List / Deliverables

### Create a JavaScript file
- [ ] Create a folder called `js` at the same level as your index.html, readme.md, and your css folder.
- [ ] Inside the js folder, create a JavaScript file called `index.js`
- [ ] Open your `index.html` file
- [ ] Before the closing `</body>` tag, insert a `<script>` element with a `src` attribute that specifies the relative path to your JavaScript file (i.e. `js/index.js`)
- [ ] Save and open the index.html in your browser so you can check your changes to your html page as you build the js code below.  _If you're using VSCode or similar, you should be able to install/may already have an extension that allows you to have a "live" version of your index.html running in your browser that will automatically update when changes in your files are saved so you don't have to keep refreshing your file in your browser._

### Add a Footer Element
- [ ] In your index.js file, using DOM manipulation, add a 'footer' child element to your index.html.  Be careful on this step, as different DOM methods (append, appendChild, lastChild, etc.) have different placements.
- [ ] Remember that you can store the elements in variables to reference the variables and call methods on them to more easily follow your code. (It's easier to read `body.innerHTML` than it is to read `document.getElementsByTagName("body").innerHTML`)

### Insert Copyright Text in Footer
- [ ] Open your `index.js` file
- [ ] Create a variable named `today` and assign it a new date object
  - hint: `new Date()` constructor
- [ ] Create a variable named `thisYear` and assign it the current year from your date object. Use a method to do this, don't hardcode "2024" because next year your website will have the wrong year! 
  - hint: `getFullYear` method
- [ ] Create a variable named `footer` and assign it the footer element by using "DOM Selection" to select the `<footer>` element from the DOM
  - hint: `querySelector` method or similar
- [ ] Create a variable named `copyright` and use it to create a new paragraph (`p`) element
  - hint: `createElement` method
- [ ] Set the inner HTML of your `copyright` element to display your name and the current year
  - hint: use the `copyright` variable and the `thisYear` variable from earlier
- [ ] Append the `copyright` element to the footer using "DOM Manipulation"
  - hint: `appendChild` method or similar
- [ ] STRETCH GOAL: Use unicode to also include the copyright symbol ( &copy; ) in your footer content
- [ ] Save and refresh your browser
  - You should see the text "_Your Name_ 2024" at the bottom of the page

### Add to your Skills Section
- [ ] Open your `index.html` file
- [ ] Above the "Connect" section, add a new `<section>` element with an `id` attribute of value "skills"
- [ ] Inside the new section, add a `<h2>` element that says "Skills"
- [ ] After the `<h2>` element, add an empty unordered list (`<ul>`) element
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_
  - You should see the new "Skills" heading

### Create List of Skills
- [ ] Open your `index.js` file
- [ ] List your technical skills by creating an Array of String values and store it in a variable named `skills`.  You did something very similar in Assignment 2.
  - Example: `["JavaScript", "HTML", "CSS", "Adobe Photoshop", "GitHub"]`
- [ ] Create a variable named `skillsSection` and use "DOM Selection" to select the skills section by id
  - hint: `querySelector` or `getElementById` method
- [ ] Create a variable named `skillsList` and use "DOM Selection" to query the `skillsSection` (instead of the entire `document`) to select the `<ul>` element you created earlier in this assignment
- [ ] Create a `for` loop to iterate over your `skills` Array
- [ ] Inside the loop, create a variable named `skill` to create a new list item (`li`) element
  - hint: `createElement` method
- [ ] Still inside the loop, use the `skill` variable to set the inner text to the current Array element
  - hint: access the Array element using bracket notation
- [ ] The last thing we'll do inside the loop is append the `skill` element to the `skillsList` element
  - hint: `appendChild` method
- Save and refresh your browser _(or just check your browser for changes if using live extension)_
  - You should see your list of skills beneath the "Skills" heading
 
### Style your skills
 - [ ] Open your `index.css` file
 - [ ] Use flexbox or grid to organize and adjust the layout of your list of skills.  Remember to include any adjustments in your media query sections.

**_By the end of this assignment, you should have a js folder with an index.js in it.  The code you wrote in your index.js should have written a footer with your name and the current year to the html document.  Also, an array list of skills in your index.js file should be written to the skills section you created in your html document and should be styled using flexbox or grid._**

## Back up to the cloud
Once you've made the above changes to your html file, follow the below instructions to push a copy from your local machine like you did at the end of last assignment. Make sure your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:

- [ ] Check the status of the changes you just made (creating a js folder and the index.js file within, linking the index.js to your html file) by running git status in your terminal
- [ ] Stage all your changes for commit by running `git add .` in your terminal
- [ ] Run `git status` again to see how things have changed. You should get a response indicating changes staged for commit.
- [ ] Create a commit message for reference. You can use a different message if you wish. Run `git commit -m "js added, created footer and skills"`
- [ ] Push these changes to your GitHub repository from your local computer by running `git push`

## Submit Assignment
Now let's make sure that lesson branch will be reviewed.

- [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-7 has a recent push" notice with a green "Compare & pull request" button. Click that button
- [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
- [ ] Copy the address of your pull request page (should look something like https://github.com/yourUsername/name-classname/pull/#) and paste it into your assignment submission form.

## What next?
   - If you are ready to start on the next lesson and have not gotten your review comments back yet, you can go ahead and merge your pull request and continue working.
   - if you are unsure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.
