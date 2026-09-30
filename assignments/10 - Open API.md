### Get organized and write some code!
- [ ] In your GitHub repository, if you have not yet merged your pull request from last week, merge your open lesson-9 pull request by going to the "Pull Requests" tab of your repository. Click on your open pull request, then click on the green 'Merge Pull Request" and confirm the merge. This will update your main branch with the work you did on your lesson-9 branch.
- [ ] Open your code editor and, in the terminal, make sure you're on your main branch. If you're still on your lesson-9 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-9 work by pulling your changes from your GitHub repository main. Use the following git command in your terminal to do this: `git pull origin main`
- [ ] Still in your terminal, create a new local branch to keep track of just the work you'll do for this assignment by running `git checkout -b lesson-10` in the terminal. Doing this also copies the lesson-9 work you merged to main and pulled to your local machine so now all your branches should be identical on your local machine.

### Assignment: Task List / Deliverables

**NOTE:** This week you build a new Open API page that links to and from the portfolio site you have been building since Assignment 5. Keep all of your existing work; this assignment adds a new page to it.

There is a lot of freedom on this page to be creative. You may structure and style the page any way you like, as long as it meets the requirements below.

#### Set up the page
- [ ] Create a new HTML file for your Open API page.
- [ ] Create a new CSS file to style the page. You may also link your portfolio's existing CSS file if you want to reuse some styles.
- [ ] Create a new JavaScript file for the code that gets data from the API.
- [ ] Add a link to the new page in your portfolio's nav bar.
- [ ] Add a nav bar to the new page with a link back to your portfolio page.

#### Choose an API
- [ ] Choose a public API that has at least two endpoints. An endpoint is a specific URL that returns a specific type of data. For example, the Dog API has one endpoint that returns a list of dog breeds (`https://dog.ceo/api/breeds/list/all`) and a different endpoint that returns a random dog photo (`https://dog.ceo/api/breeds/image/random`). This is only an example. You can use any public API.

#### Get and display the data
- [ ] Display data from at least two different endpoints of your API. Using more than two endpoints is optional.
- [ ] Add a navigation button or link for each type of data so the user can switch between them. For example, with the Dog API, one button shows the list of breeds and another button shows a random dog photo.
- [ ] Write a separate GET request for each navigation option. Each request should call only the endpoint needed for the data that option displays. Do not get all of the data in one request and then filter it.
- [ ] You may load one type of data by default when the page first opens.
- [ ] Handle errors in each request: check `response.ok`, and use `.catch` (or `try`/`catch`) so a failed request does not break your page. Report the error, either with a message on the page or with a message in the console.

#### (Optional) Update your README
- [ ] (Optional) Add a short section to your portfolio's README file that explains how to run your site. For example, which file to open in the browser, or how to start it with Live Server.

#### How your work will be reviewed
Your reviewer will check that:
- Your code runs without errors.
- Switching between the types of data works correctly.
- Your code is readable and well organized.
- Failed requests are handled.
- Your styling is easy to read: font sizes are not too small or too large, and text colors contrast clearly with the background.

### Back up to the cloud
Once you've made the above changes to your files, follow the below instructions to push a copy from your local machine like you did at the end of last assignment. Make sure your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:

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
 - If you are unsure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.

---

<details>
<summary>Rubric (for AirHub reviewer and mentors)</summary>

The reviewer cannot run the student's code, call the live API, or see the rendered page. Grade the structure and correctness of the code. This rubric is the complete set of requirements. Do NOT apply criteria from any other page or lesson.

### Required Deliverables/Tasks

- **Cumulative work** — This assignment adds a new page to the portfolio site built in Assignments 5 through 9. All existing portfolio files, including the existing README, are expected. Do NOT treat prior-week work as stray or tell the student to remove it.

- **Three new files for the page** — A new HTML file, a new CSS file, and a new JavaScript file for the Open API page. The page may also link the portfolio's existing CSS file in addition to its own. File names and folder locations are the student's choice. Do NOT fail a student for naming or placement.

- **Two-way navigation between pages** — The portfolio's nav bar links to the new page, and the new page has a nav bar that links back to the portfolio.

- **Choice of API** — Any public API with at least two endpoints. The Dog API in the assignment is an example only. Do NOT require a particular API or particular endpoints.

- **At least two endpoints** — The page displays data from at least two different endpoints (different URLs), not the same endpoint called with different parameters. More than two is allowed and is not required.

- **Navigation between data types** — A button or link for each type of data, so the user can switch between them.

- **Separate GET request per navigation option** — Each navigation option triggers its own GET request to the endpoint for the data it displays. A student who fetches all data in one request and filters it on the client has NOT met this requirement. Do NOT fail a student for loading one data type by default when the page opens, or for storing a response so a repeated click does not fetch again. Do NOT fail a student because an endpoint returns more fields than the page displays, since students usually cannot control an API's response.

- **Error handling** — Each request checks `response.ok` (or an equivalent check of the response status) and catches failed requests with `.catch` or `try`/`catch`. How the error is reported (a message on the page or in the console) is the student's choice.

- **Code quality** — Readable, reasonably organized code. Judge generously: this is an intro course, and the assignment gives students freedom in how they structure the page. Do NOT fail a student for style preferences or for not using a pattern the assignment does not ask for.

- **Effective styling** — Judged from the CSS: font sizes that are neither very small nor very large, and text and background colors with enough contrast. All specific colors, fonts, and layout choices are the student's own. There is no correct design.

- **Submission** — A pull request from the `lesson-10` branch, with its link submitted in the assignment form.

### Optional Deliverables/Tasks

Do NOT fail a student for omitting these.

- **README running instructions** — A section in the portfolio README explaining how to run the site. If present, any clear format is acceptable. A README with only the student's name, course, and program is complete for this assignment.
- **More than two endpoints** — Additional endpoints and navigation options beyond the required two.

</details>
