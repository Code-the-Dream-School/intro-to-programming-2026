### Get organized and write some code!
- [ ] In your GitHub repository, if you have not yet merged your pull request from last week, merge your open lesson-9 pull request by going to the "Pull Requests" tab of your repository. Click on your open pull request, then click on the green 'Merge Pull Request" and confirm the merge. This will update your main branch with the work you did on your lesson-9 branch.
- [ ] Open your code editor and, in the terminal, make sure you're on your main branch. If you're still on your lesson-9 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-9 work by pulling your changes from your GitHub repository main. Use the following git command in your terminal to do this: `git pull origin main`
- [ ] Still in your terminal, create a new local branch to keep track of just the work you'll do for this assignment by running `git checkout -b lesson-10` in the terminal. Doing this also copies the lesson-9 work you merged to main and pulled to your local machine so now all your branches should be identical on your local machine.

### Assignment: Task List / Deliverables

**NOTE:** This week you build a new Open API page that links to and from the portfolio site you have been building since Assignment 5. Keep all of your existing work — this assignment adds a new page to it.

- [ ] Review the requirements below (also available as the [Open API Rubric](https://github.com/Code-the-Dream-School/intro-to-programming-2026/wiki/Open-API-Rubric) in the course wiki), then use your own creativity and the skills you have learned so far in the class to create a page that meets them.

There is a lot of freedom on this page to be creative.  You may structure and style this page any way you would like.  It must meet the following minimal requirements.

#### STRUCTURE:
- [ ] Linked to the page from the portfolio nav bar
- [ ] Nav bar that allows navigation back to the portfolio page
- [ ] An HTML document for the page
- [ ] A CSS document to style the HTML page
- [ ] A JavaScript file that retrieves data from one of several public API sources to display the data on your HTML page

#### CONTENT:
- [ ] Display the data for at least 2 endpoints in the API
- [ ] Include navigation (e.g. button or link) from each type of data to the other (For Example: if using the weather app, one navigation button/link should display the temperature details and the second navigation button/link should display the weather condition)
- [ ] Issue new GET requests each time the user clicks a navigation link, meaning you should have 2 GET requests - one for each navigation, that requests only the needed information (Example: if using the weather app, clicking temperature navigation link should pull only data that allows user to see temperatures and clicking conditions navigation link should pull only data that allows user to see weather conditions)

#### FUNCTIONALITY:
- [ ] Code runs without issues by following the instructions in the README file
- [ ] Navigation between the different endpoints behaves properly and is not slowed down by requesting more data than needs to be displayed (this is the reason for the 2 separate GET requests)
- [ ] Code is readable and well structured
- [ ] If applicable, error cases are appropriately handled
- [ ] Styling is effective (example: font-sizes are not too small or large, colors are not too dark/light to be easily seen, etc.)

### Back up to the cloud
Once you've made the above changes to your html file, follow the below instructions to push a copy from your local machine like you did at the end of last assignment. Make sure your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:

- [ ] Check the status of the changes you just made by running git status in your terminal
- [ ] Stage all your changes for commit by running `git add .` in your terminal
- [ ] Run `git status` again to see how things have changed. You should get a response indicating changes staged for commit.
- [ ] Create a commit message for reference. You can use a different message if you wish. Run `git commit -m "added open api page"`
- [ ] Push these changes to your GitHub repository from your local computer by running `git push`

### Submit Assignment
Now let's make sure that lesson branch will be reviewed.

- [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-10 has a recent push" notice with a green "Compare & pull request" button. Click that button
- [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
- [ ] Copy the address of your pull request page (should look like https://github.com/yourUsername/name-classname/pull/#) and paste it into your assignment submission form.

## What next?
 - If you are ready to start on the next lesson and have not gotten your review comments back yet, you can go ahead and merge your pull request and continue working.
 - if you are unsure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.

---

<details>
<summary>Rubric (for AirHub reviewer and mentors)</summary>

### Required Deliverables/Tasks

- **Cumulative work** — This assignment adds a new Open API page to the portfolio site built across Assignments 5 through 9. All existing portfolio work must still be present. Do NOT treat prior-week content as stray or tell the student to remove it.

- **Three separate files** — An HTML document for the new page, a CSS document that styles it, and a JavaScript file that retrieves the API data. These are separate from the portfolio's own `index.*` files. File names and folder locations are the student's own choice — Example, adapt to your own layout; the assignment specifies none. Do NOT fail a student for naming or placement, which the reviewer generally cannot verify.

- **Two-way navigation between the pages** — The new page is linked from the portfolio's nav bar, and the new page has a nav bar with a link back to the portfolio page.

- **Choice of API** — The JavaScript retrieves data from a public API source of the student's choosing — Example; any public API with at least two endpoints satisfies this. Do NOT require a particular API, a particular pair of endpoints, or the weather API used in the assignment's examples.

- **Data from at least two endpoints** — The page displays data from two or more endpoints of that API.

- **Navigation between the data types** — A button or link for each type of data, letting the user move from one to the other.

- **Two separate GET requests** — A new GET request issued on each navigation click — two requests total, one per navigation — each requesting only the data that navigation needs. A student who fetches everything once up front and filters client-side has not met this requirement, since the point is the separate targeted requests.

- **Runs from the README** — The code runs without issues when someone follows the instructions in the README file, which means those instructions must exist. Their format and level of detail are the student's own — Example.

- **Navigation performance** — Navigation between endpoints behaves properly and is not slowed by requesting more data than it displays.

- **Code quality** — Code that is readable and well structured. Judge this generously: this is an intro course, and the assignment explicitly grants freedom in how the page is structured. Do NOT fail a student for style preferences, formatting, or not using a pattern the assignment never asked for.

- **Error handling — conditional** — The requirement is "**If applicable**, error cases are appropriately handled." Treat this as conditional: do NOT fail a student for the absence of error handling unless their chosen API and page clearly call for it. Any reasonable approach satisfies it; no specific pattern or message is required.

- **Effective styling** — Font sizes that are neither too small nor too large, and colors with enough contrast to be easily seen. All specific colors, fonts, and layout choices are the student's own — Example; there is no correct design here, and the assignment says the student may style the page any way they like.

- **Submission** — A pull request from the `lesson-10` branch, with its link submitted in the assignment form. Verified by the submitted link.

- **Not deliverables** — The reviewer cannot run the student's code or call the live API, so grade the structure and correctness of the code rather than observed output. Every requirement from the linked wiki rubric is restated above, so do NOT look to the wiki (or to any other lesson) for additional criteria, and do NOT fail a student against requirements not listed here.

### Optional Deliverables/Tasks

None. The Open API rubric contains no optional items — every requirement is required. The freedom the assignment grants in structure and styling is reflected in the leniency notes above, not as skippable work.

</details>
