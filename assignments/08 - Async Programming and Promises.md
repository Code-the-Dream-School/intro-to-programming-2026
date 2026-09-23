## Get organized and write some code!
- [ ] In your GitHub repository, if you have not yet merged your pull request from last week, merge your open lesson-7 pull request by going to the "Pull Requests" tab of your repository. Click on your open pull request, then click on the green 'Merge Pull Request" and confirm the merge. This will update your main branch with the work you did on your lesson-7 branch.
- [ ] Open your code editor and, in the terminal, make sure you're on your main branch. If you're still on your lesson-7 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-7 work by pulling your changes from your GitHub repository main. Use the following git command in your terminal to do this: `git pull origin main`
- [ ] Still in your terminal, create a new local branch to keep track of just the work you'll do for this assignment by running `git checkout -b lesson-8` in the terminal. Doing this also copies the lesson-7 work you merged to main and pulled to your local machine so now all your branches should be identical on your local machine.

### Assignment: Task List / Deliverables

**NOTE:** This week builds on the work from Assignments 5 through 7. Keep your existing `index.html` sections, your `css/index.css` styles, and the JavaScript you already wrote in `js/index.js` — this assignment adds to all three.

#### Create a Message Form
- [ ] Open your `index.html` file
- [ ] Above the `<script>` element, add an empty `<section>` element with an `id` so your nav link can jump to it (use the same convention you used for your other sections in Assignment 6)   Note: the Message Form should be the last section on your portfolio page above the footer.  The footer was added in javascript, so it will not be in the index.html.
- [ ] Inside the new `<section>` element, create a level-two heading that says "Leave a Message"
- [ ] After the heading, create an HTML `<form>` element with a `name` attribute that equals "leave_message"
- [ ] Inside the `<form>` element, add the following:
  1. `<input>` element with attributes: `type` "text", `name` "usersName", and `required` true
  2. `<input>` element with attributes: `type` "email", `name` "usersEmail", and `required` true
  3. `<textarea>` element with attributes: `name` "usersMessage" and `required` true
  4. `<button>` element that says "Submit" and has `type` attribute equal to "submit"
  5. Each form field should also have a corresponding `<label>` element
  6. (Optional) Use `<br>` elements to stack the form fields
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_
- [ ] Add navigation to the message form:
  - [ ] Add a link in your `<nav>` section that takes the user to the 'Leave a Message' section when clicked

#### Add Message List Section
- [ ] After the `<section>` element from the previous step, create a new `<section>` element with an `id` of "messages"
- [ ] Inside that element, create a level-two heading that says "Messages"
- [ ] After the heading, add an empty unordered list (`<ul>`) element
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_

#### Handle Message Form Submit
- [ ] Open your `index.js` file and start at the bottom
- [ ] Create a variable named `messageForm` that uses "DOM Selection" to select the "leave_message" form by `name` attribute
- [ ] Add an event listener to the `messageForm` element that handles the "submit" event
  - hint: `addEventListener` method
- [ ] Inside the callback function for your event listener, create three new variables (one for each of the three form fields) and retrieve the value from the event
  - hint: `event.target` is the form, `event.target.usersName` is the first input element
- [ ] Inside the callback function for your event listener, add a `console.log` statement to log the three variables you created in the previous step
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_
- [ ] Open the console in your browser if you haven't already by either right clicking on your page and select "Inspect" or by using the menu bar to open the Developer tools. 
 - [ ] Fill out the HTML form in your browser and hit "Submit"

> Note: at this point, you should notice that the browser is refreshing automatically when you submit your form which is **_not_** the desired behavior

- [ ] Inside the callback function, above the other code you just wrote, add a new line to prevent the default refreshing behavior of the "submit" event
  - hint: `preventDefault` method
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_
- [ ] Fill out the HTML form in your browser and hit "Submit"
  - You should see that the page **does not** refresh and your values are logged in the console

> Note: at this point, you should notice that the form is submitting properly but the form fields are not reset after submit

- [ ] Inside the callback function, on the very last line, add a new line of code to clear the form
  - hint: `reset` method
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_

#### Display Messages in List
- [ ] In the `index.js` file, start inside the event listener callback function on the line **above** where you reset the form
- [ ] Create a variable named `messageSection` and use "DOM Selection" to select the #messages section by `id`
- [ ] Create a variable named `messageList` and use "DOM Selection" to query the `messageSection` (instead of the entire `document`) to find the `<ul>` element
- [ ] Create a variable named `newMessage` that makes a new list item (`li`) element
- [ ] On the next line, set the inner HTML of your `newMessage` element with the following information:
  - `<a>` element that displays the "usersName" and is a clickable link to the "usersEmail" (hint: use the `mailto:` prefix)
  - `<span>` element that displays the "usersMessage"
- [ ] Create a variable named `removeButton` that makes a new `<button>` element
  - Set the inner text to "remove"
  - Set the `type` attribute to "button"
  - Add an event listener to the `removeButton` element that handles the "click" event
    - Inside the callback function, create a variable named `entry` that finds the button's parent element using DOM Traversal (hint: `parentNode` property)
    - Remove the `entry` element from the DOM (hint: `remove` method)
- [ ] Append the `removeButton` to the `newMessage` element
  - hint: `appendChild` method
- [ ] Append the `newMessage` to the `messageList` element
- [ ] Save and refresh your browser _(or just check your browser for changes if using live extension)_

#### Style your Message Form
 - [ ] Open your `index.css` file
 - [ ] Style your message form fields and buttons keeping in mind:
   - [ ] adequate spacing so form fields aren't crowded
   - [ ] appropriate sizing in media queries so a user on a mobile device can easily touch/tap into the fields to type
   - [ ] button sizing to accommodate click and touch/tap interactions

#### Optional Tasks
These tasks are **entirely optional**, but if you'd like a challenge then do your best to complete each item.
- [ ] (Optional) Hide the #messages section, including the Messages header, when the list is empty
- [ ] (Optional) Create an "edit" button for each message entry that allows the user to input a new/modified message

**_By the end of this assignment, you should have a form in your HTML document with name, email, message fields and a submit button as well as a messages section.  The code you wrote in your index.js should handle the inputs the user enters into the form and display that information as a name you can click on to email the user and their message with a remove button to remove their message entirely.  You should have styling in your index.css file for your message form fields and/or section.  If you attempted the optional tasks, you should also have a hidden Messages section unless there is a message and/or each message should have an edit button._**

### Backup to the cloud
Once you've made the above changes to your html file, follow the below instructions to push a copy from your local machine like you did at the end of last assignment. Make sure your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:

- [ ] Check the status of the changes you just made (code changes to the index.html and index.js files) by running git status in your terminal
- [ ] Stage all your changes for commit by running `git add .` in your terminal
- [ ] Run `git status` again to see how things have changed. You should get a response indicating changes staged for commit.
- [ ] Create a commit message for reference. You can use a different message if you wish. Run `git commit -m "form and functionality added"`
- [ ] Push these changes to your GitHub repository from your local computer by running `git push`

### Submit Assignment
Now let's make sure that lesson branch will be reviewed.

- [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-8 has a recent push" notice with a green "Compare & pull request" button. Click that button
- [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
- [ ] Copy the address of your pull request page (should look something like https://github.com/yourUsername/name-classname/pull/#) and paste it into your assignment submission form.

## What next?
   - If you are ready to start on the next lesson and have not gotten your review comments back yet, you can go ahead and merge your pull request and continue working.
   - if you are unsure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.

---

<details>
<summary>Rubric (for AirHub reviewer and mentors)</summary>

### Required Deliverables/Tasks

- **Cumulative work** — This assignment builds on Assignments 5 through 7. The existing `index.html` sections, `css/index.css` styles, and `js/index.js` code (the footer and skills list) must still be present; this week adds to all three. Do NOT treat prior-week content as stray or tell the student to remove it. Note that the footer is created in JavaScript, so it correctly does not appear in `index.html` — the assignment says so explicitly.

- **Message form section (`index.html`)** — A `<section>` placed above the `<script>` element, as the last section of the page, carrying an `id` so the nav link can target it (any id value is acceptable as long as the nav link points to it). Inside it: an `h2` reading "Leave a Message" (use exactly as written), then a `<form>` with `name="leave_message"` (use exactly as written — the JavaScript selects the form by this name). Inside the form: a text `<input>` named `usersName`, an email `<input>` named `usersEmail`, and a `<textarea>` named `usersMessage`, all three `required`; a `<button>` reading "Submit" with `type="submit"`; and a `<label>` for each of the three fields. Use exactly as written for all three field names — the JavaScript depends on them.

- **Navigation** — A link added to the existing `<nav>` that jumps to the message form section.

- **Messages list section (`index.html`)** — A `<section>` with `id="messages"` placed after the message form section, containing an `h2` reading "Messages" and an empty `<ul>`. Use exactly as written for the id and heading.

- **Handle form submit (`index.js`)** — A variable named `messageForm` selecting the form by its `name` attribute (use exactly as written), with a "submit" event listener attached. Inside the callback: three variables holding the three submitted field values — the assignment does not specify names for these three, so any reasonable names are acceptable (Example) — and a `console.log` of all three (the log's format is the student's own). The callback must also prevent the submit event's default page-refresh behavior, and the `reset` call to clear the form should be the last line in the callback, as instructed.

- **Display messages in list (`index.js`, inside the same callback, above the reset)** — Variables named `messageSection` (selecting `#messages` by id), `messageList` (querying **within `messageSection`**, not the whole document, for the `<ul>`), and `newMessage` (a new `li`). Use exactly as written for these names. The `newMessage` content must include an `<a>` element showing the submitted name that links to the submitted email using a `mailto:` link, and a `<span>` showing the submitted message. Also a variable named `removeButton`: a new `<button>` with inner text "remove" and `type="button"` (use exactly as written), carrying a "click" listener whose callback creates a variable named `entry` holding the button's parent element via DOM traversal and removes that element from the DOM. `removeButton` appended to `newMessage`, and `newMessage` appended to `messageList`.

- **Style the message form (`index.css`)** — The message form fields and buttons styled, addressing spacing, field sizing for mobile touch targets, and button sizing. The three sub-points are given as things to keep in mind — a student who achieves usable mobile sizing without a literal `@media` block should NOT be failed for the absence of a media query. All specific values and design choices are the student's own — Example.

- **Submission** — A pull request from the `lesson-8` branch, with its link submitted in the assignment form. Verified by the submitted link, not by code beyond `index.html`, `css/index.css`, and `js/index.js`.

- **Not deliverables** — The repeated "Save and refresh your browser," "Open the console in your browser," and "Fill out the HTML form in your browser and hit Submit" steps are actions the student performs while working. They leave no trace in the code and cannot be verified — do NOT grade them. The two `> Note:` blocks describing the page refreshing and the fields not clearing are describing *intermediate* states in a teaching sequence, not desired end behavior: the finished code must prevent the default refresh and must reset the form. DOM method hints are flexible — `getElementById` for `querySelector`, `append` for `appendChild`, and any correct way of reading the field values (such as `event.target.usersName.value`) are all acceptable.

### Optional Deliverables/Tasks

Do not fail a student for omitting any of these. The assignment marks each one "(Optional)" and says the final section is "entirely optional."

- Using `<br>` elements to stack the form fields.
- Hiding the `#messages` section, including the "Messages" heading, when the list is empty.
- Adding an "edit" button to each message entry that lets the user submit a new or modified message.

</details>
