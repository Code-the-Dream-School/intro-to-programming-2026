## Get organized and write some code!
- [ ] In your GitHub repository, if you have not yet merged your pull request from last week, merge your open lesson-8 pull request by going to the "Pull Requests" tab of your repository. Click on your open pull request, then click on the green 'Merge Pull Request" and confirm the merge. This will update your main branch with the work you did on your lesson-8 branch.
- [ ] Open your code editor and, in the terminal, make sure you're on your main branch. If you're still on your lesson-8 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-8 work by pulling your changes from your GitHub repository main. Use the following git command in your terminal to do this: `git pull origin main`
- [ ] Still in your terminal, create a new local branch to keep track of just the work you'll do for this assignment by running `git checkout -b lesson-9` in the terminal. Doing this also copies the lesson-8 work you merged to main and pulled to your local machine so now all your branches should be identical on your local machine.

### Assignment: Task List / Deliverables

**NOTE:** This week builds on the work from Assignments 5 through 8. Keep your existing `index.html` sections, your `css/index.css` styles, and the JavaScript you already wrote in `js/index.js` — this assignment adds to them. Your new code goes below the code you wrote last week, and it fills the empty `<ul>` in the Projects section you created in Assignment 6.

#### Creating your fetch
- [ ] Open your `index.js` file, starting below the code from the previous lesson
- [ ] Using the Fetch API, create a "GET" request to `https://api.github.com/users/{GITHUB_USERNAME}/repos` where `{GITHUB_USERNAME}` is your username for your GitHub account
  - hint: the `fetch` function
  - hint: "GET" is the default method for `fetch`
- [ ] Chain a `then` method to your `fetch` call and pass it a function that returns the response JSON data

#### Handle your JSON data
- [ ] Chain another `then` method and pass it a callback function to parse the response and store it in a variable named `repositories`
  - hint: the value passed into this callback is already the parsed JSON (from the `.then` above) — just assign it to `repositories`
- [ ] Console.log the value of repositories to better see the data returned from your API fetch
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_
  - You should see the list of your GitHub repositories displayed in your console.

#### Handling errors
 - [ ] Chain a `catch()` function to your `fetch` call to handle errors from the server so the user would know what happened if your Projects section was empty.

#### Display Repositories in List
 - [ ] Create a variable named `projectSection`; using "DOM Selection" to select the projects section by id
 - [ ] Create a variable named `projectList`; using "DOM Selection" query the projectSection (instead of the entire document) to select the <ul> element
 - [ ] Create a for loop to iterate over your repositories Array, starting at index 0
   - [ ] Inside the loop, create a variable named `project` to make a new list item (li) element
     - hint: createElement method
   - [ ] On the next line, set the inner text of your project variable to the current Array element's name property
     - hint: access the Array element using bracket notation
   - [ ] On the next line, append the project element to the projectList element
     - hint: appendChild method
 - [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_
   - You should see your list of repositories beneath the "Projects" heading on your portfolio site
      
#### Style your Repository List
 - [ ] Open your `index.css` file
 - [ ] Add styling to your projects list, be sure to account for any changes you want in media queries
 - [ ] OPTIONAL: Use flexbox (or grid) to style your list of repositories

**_By the end of this assignment, you should have a working API fetch to your GitHub account and be able to see a list of your repository names in the Projects section of your portfolio.  Were there to be a server error during the API fetch, your site would return an error message.  Your project list should also have styling in your index.css file.  If you attempted the optional task, your list should be styled using flexbox or grid._**

### Backup to the cloud
Once you've made the above changes to your index.js file, follow the below instructions to push a copy from your local machine like you did at the end of last assignment. Confirm your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:

- [ ] Check the status of the changes you just made (code changes to the index.js files) by running git status in your terminal
- [ ] Stage all your changes for commit by running `git add .` in your terminal
- [ ] Run `git status` again to see how things have changed. You should get a response indicating changes staged for commit.
- [ ] Create a commit message for reference. You can use a different message if you wish. Run `git commit -m "API fetch completed"`
- [ ] Push these changes to your GitHub repository from your local computer by running `git push`

### Submit Assignment
Now let's make sure that lesson branch will be reviewed.

- [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-9 has a recent push" notice with a green "Compare & pull request" button. Click that button
- [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
- [ ] Copy the address of your pull request page (should look like https://github.com/yourUsername/name-classname/pull/8) and paste it into your assignment submission form.  **_NOTE: If you'd like your reviewer to check your open API project work in progress, submit the link in the "questions" field of your assignment submission form._**

### What next?
- If you're on track with class, wait to get feedback and/or the email notice that your assignment review is complete before confirming and merging your pull request to the main branch.
- If you're behind or are working ahead:
  - if you're confident your work is accurate, merge your pull request and continue working through class.
  - if you're not sure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.

---

<details>
<summary>Rubric (for AirHub reviewer and mentors)</summary>

### Required Deliverables/Tasks

- **Cumulative work** — This assignment builds on Assignments 5 through 8. The existing `index.html` sections, `css/index.css` styles, and `js/index.js` code (footer, skills list, message form handling) must still be present; this week adds to them. Do NOT treat prior-week content as stray or tell the student to remove it. The new code belongs below the previous lesson's code, and it fills the empty `<ul>` in the Projects section created in Assignment 6.

- **The fetch call (`index.js`)** — A Fetch API "GET" request to `https://api.github.com/users/{GITHUB_USERNAME}/repos`. **The URL is a template:** `{GITHUB_USERNAME}` is replaced by the student's own GitHub username — Example, adapt to your own account. Do NOT expect the literal text `{GITHUB_USERNAME}` in the submitted code, and do NOT fail a student for using their real username, which is exactly what the assignment asks for. Because "GET" is the default method for `fetch`, code that omits an explicit method is correct.

- **Chained `then` for JSON** — A `then` chained to the fetch, passed a function that returns the response's JSON data.

- **Chained `then` for the data** — A second `then` whose callback stores the parsed data in a variable named `repositories` (use exactly as written), plus a `console.log` of that variable. The log's format is the student's own — Example.

- **Error handling** — A `catch()` chained to the fetch call to handle server errors. Either handling approach satisfies this: logging the error, or displaying a message to the user. Do NOT fail a student whose catch logs the error rather than rendering an on-page message.

- **Display repositories in list (`index.js`)** — Variables named `projectSection` (selecting the Projects section by id) and `projectList` (querying **within `projectSection`**, not the whole document, for the `<ul>`). Use exactly as written for both names. A `for` loop over the `repositories` array starting at index 0; inside the loop, a variable named `project` holding a newly created `li` (use exactly as written) whose inner text is set to the current array element's `name` property, appended to `projectList`.

- **Where this code lives** — `repositories` exists inside the `then` callback, so the display code must be positioned where that variable is in scope. Accept any correct structure — code written directly inside the `then`, or a function defined elsewhere and called from it — as long as the data is in scope when it is used.

- **Style the repository list (`index.css`)** — Styling added for the projects list. Media queries are discretionary here: the assignment says "account for any changes you want in media queries," so do NOT fail a student who has no `@media` block. All specific values and design choices are the student's own — Example.

- **Submission** — A pull request from the `lesson-9` branch, with its link submitted in the assignment form. Verified by the submitted link, not by code beyond `index.js` and `index.css`.

- **Not deliverables** — The "Save and refresh your browser" steps are actions the student performs while working; they leave no trace in the code and cannot be verified, so do NOT grade them. This assignment calls a live external API, which the reviewer cannot run: grade the structure and correctness of the fetch chain, not whether repository names actually appear. DOM and Fetch method hints are flexible — `getElementById` for `querySelector` and `append` for `appendChild` are both acceptable — but the `then`/`catch` chaining pattern is explicitly required by the assignment.

### Optional Deliverables/Tasks

Do not fail a student for omitting this. The assignment marks it as "Optional" (originally "Stretch Goal").

- Using flexbox (or grid) to style the list of repositories.

</details>
