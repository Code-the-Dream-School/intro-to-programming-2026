## Get organized and write some code!
- [ ] In your GitHub repository, if you have not yet merged your pull request from last week, merge your open lesson-5 pull request by going to the "Pull Requests" tab of your repository. Click on your open pull request, then click on the green 'Merge Pull Request" and confirm the merge. This will update your main branch with the work you did on your lesson-5 branch.
- [ ] Open your code editor and, in the terminal, make sure you're on your main branch. If you're still on your lesson-5 branch, you can switch to your main branch by using the git command `git checkout main`.
- [ ] Update your local main branch to include your lesson-5 work by pulling your changes from your GitHub repository main. Use the following git command in your terminal to do this: `git pull origin main`.
- [ ] Still in your terminal, create a new local branch to keep track of just the work you'll do for this assignment by running `git checkout -b lesson-6` in the terminal. Doing this also copies the lesson-5 work you merged to main and pulled to your local machine so now all your branches should be identical on your local machine.

## Assignment: Task List / Deliverables

**NOTE:** This week builds on the `index.html` page you created in Assignment 5. Keep all of your existing content — your name, and your About, Experience, and Connect sections. This assignment adds styling and two new sections to that page.

### Create and Load Stylesheet
   - [ ] Create a **_folder_** called `css` at the same level as your README.md and index.html files
   - [ ] Inside that folder, create a Cascading Style Sheets (CSS) file called `index.css`
   - [ ] Open your `index.html` file
   - [ ] Before the closing `</head>` tag, insert a `<link>` element with a `rel` attribute of "stylesheet" and an `href` attribute that specifies the relative path to your CSS file (i.e. `css/index.css`)

### Write CSS
For this assignment, there are some general requirements but the design is up to you! This is your chance to be creative and transform your webpage into a reflection of who you are.  We suggest starting small with background colors, font choices, etc.  Make small changes, verify they work as expected, then proceed to the next change.  **TIP:** If you're struggling with visualizing sections of your webpage, put colorful borders around each section so you can see how changing your css code changes a given section.
   - [ ] Change the background color of the page body
   - [ ] Change the default text color
   - [ ] Customize the font family
     - [ ] OPTIONAL: load in a font family from [Google Fonts](https://fonts.google.com/)
   - [ ] Add spacing (padding/margin) between sections
   - [ ] Change the alignment of the content of one of your sections
   - [ ] Change the font size, weight, and color of headings
   - [ ] Transform the style of your Name at the top of the page
     - [ ] OPTIONAL: add a picture of yourself to HTML and/or CSS (remember to include accessibility aspects if you add any images!)
   - [ ] Transform the "Experience" list items into styled blocks
   - [ ] Transform the style of the "Connect" links
     - [ ] OPTIONAL: make or use social media icons to replace your link text with images

**_By the end of this section, you should have basic styling and have changed a minimum of one background color, one font, one text color, the padding and margin of one element, the alignment of one element, the look of the heading elements, the look of your name, the look of list items, the look of links._**

### Now let's do a little formatting
   - [ ] In your index.html file, add a navigational header to your webpage using the `<nav>` element.
   - [ ] Add two sections to your index.html file:
     - [ ] The first section will be "Skills".  Use an h2 tag as you did with your About, Experience, and Connect sections, and be sure to include the id property in the element.  Below the heading, add an empty `<ul>` element.  Leave it empty for now — in Lesson 7 you will use JavaScript to fill it with a list of your skills.
     - [ ] The second section will be "Projects".  Use an h2 tag as you did with your About, Experience, and Connect sections, and be sure to include the id property in the element.  You need to add an empty `<ul>` element in this section; you will be adding your GitHub Projects via API call to this empty section using JavaScript later in this course.  
   - [ ] The navigation menu should include a link to each of your sections (i.e. "About", "Experience", "Skills", "Projects", "Connect")
     - [ ] OPTIONAL: Make the header sticky/fixed on the page using code in your index.css file.
   - [ ] In your index.css file, change the layout of your "Experience" section using rows and columns so items are displayed in a better layout rather than a list
         Hint: use Flexbox - we suggest have job titles to the left, dates worked that job to the right and brief description of the job below the title.
   - [ ] Also in your index.css file, update the "Connect" section to use Flexbox to improve the layout of your social media icons or links

**_By the end of this section, you should have added navigation to your site that uses internal links to "jump" the user to that section of your page.  You should also have reformatted your Experience and Connect sections using Flexbox css code.  Lastly, your site should have a header for your Skills and Projects sections, with an empty `<ul>` element in each one, but no list content in either section yet._**

**NOTE:** This is the basic rubric, but we encourage you to think beyond this list and come up with your own ideas to make your webpage unique!

## Back up to the cloud
Once you've made the above changes to your html and css files, follow the below instructions to push a copy from your local machine like you did at the end of last assignment.  Confirm that your code gets copied to GitHub by adding changes to staging, committing the staged changes, and pushing them from your local machine to GitHub:
   - [ ] Check the status of the changes you just made (editing the index.html file) by running `git status` in your terminal
   - [ ] Stage all your changes for commit by running `git add .` in your terminal
   - [ ] Run `git status` again to see how things have changed.  You should get a response indicating changes staged for commit.
   - [ ] Create a commit message for reference.  You can use a different message if you wish.  Run `git commit -m "boilerplate and content added"`
   - [ ] Push these changes to your GitHub repository from your local computer by running `git push`

## Submit Assignment
Now let's make sure that lesson branch will be reviewed.
   - [ ] Go to your GitHub repository page in your web browser now, and you should see a "lesson-6 has a recent push" notice with a green "Compare & pull request" button.  Click that button
   - [ ] Feel free to put notes to yourself or notes for your reviewer in the description (be sure you're including any questions to your reviewer in your assignment submission form though!) and click the green "Create pull request" button.
   - [ ] Copy the address of your pull request page (should look like `https://github.com/yourUsername/name-classname/pull/#`) and paste it into your assignment submission form.

## What next?
   - If you are ready to start on the next lesson and have not gotten your review comments back yet, you can go ahead and merge your pull request and continue working.
   - If you are unsure about your work this week, schedule a 1:1 session with a mentor and review your work together before merging.

---

<details>
<summary>Rubric (for AirHub reviewer and mentors)</summary>

### Required Deliverables/Tasks

- **Cumulative work** — This assignment builds on the `index.html` page from Assignment 5. The existing name, About, Experience, and Connect content must still be present; this week adds styling and two new sections. Do NOT treat prior-week content as stray or tell the student to remove it.
- **Stylesheet setup** — A folder named `css` at the same level as `README.md` and `index.html`, containing a file named `index.css`. Use exactly as written (these names are referenced by Assignment 7). In `index.html`, before the closing `</head>`, a `<link>` element with `rel="stylesheet"` and an `href` pointing to the stylesheet (`css/index.css`). Grade the `<link>` element from the HTML content, which is visible; if the reviewer cannot see the repository file tree, do NOT fail the student on folder placement, which is unverifiable.
- **CSS minimums (all in `index.css`)** — at minimum: the page body background color changed; the default text color changed; a font family set; padding/margin added between sections; the content alignment of at least one section changed; heading font size, weight, and color changed; the name at the top of the page restyled; the Experience list items styled as blocks; the Connect links styled. All specific colors, fonts, sizes, and values are the student's own design choices — Example, adapt to your own design; there is no correct palette or typeface, and any visible change satisfies each item.
- **Navigation** — A `<nav>` element added to `index.html`, containing an internal link to each section: About, Experience, Skills, Projects, Connect.
- **Two new sections in `index.html`** — a "Skills" section and a "Projects" section, each with an `h2` heading and an `id` attribute matching the section name (same convention as Assignment 5). Each of these sections must also contain an empty `<ul>` — the Skills `<ul>` is filled by JavaScript in Assignment 7, and the Projects `<ul>` by an API call later in the course. Both sections are intentionally left without list content this week — do NOT fail a student for these sections being empty; that is what the assignment asks for.
- **Experience layout** — The Experience section laid out with rows and columns (Flexbox) rather than a plain list. The suggested arrangement (job titles left, dates right, description below) is a hint — Example, adapt to your own layout; any row/column layout satisfies this.
- **Connect layout** — The Connect section updated to use Flexbox. This works with either text links or icons — icons are optional (see below), so do NOT require images here.
- **Submission** — A pull request from the `lesson-6` branch, with its link submitted in the assignment form. Verified by the submitted link, not by code beyond `index.html` and `index.css`.
- **Not a deliverable** — The TIP about putting colorful borders around sections is a temporary debugging technique for the student's own use. Do NOT require borders in the submitted CSS. Likewise, the closing note encouraging students to "think beyond this list" is encouragement, not a requirement.

### Optional Deliverables/Tasks

Do not fail a student for omitting any of these. The assignment marks all of them as "Optional" (originally "Stretch Goal").

- Loading a font family from Google Fonts.
- Adding a picture of the student to the HTML and/or CSS (if added, accessibility attributes such as `alt` text are encouraged).
- Making or using social media icons in place of the Connect link text.
- Making the navigation header sticky/fixed via `index.css`.
- Any additional creative styling beyond the required minimums.

</details>
