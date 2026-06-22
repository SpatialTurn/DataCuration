---
title: "Carpentry Introduction"
teaching: 40
exercises: 20
---

## How to Create Your Own Carpentries-Style Workshop Website Using GitHub

**A beginner-friendly guide for instructors, lesson authors, and community members**

After this lesson you will be able to:

- Create a professional-looking workshop website using The Carpentries template
- Host it for free on GitHub Pages
- Customize key information (dates, instructors, setup instructions)
- Understand why we avoid forking and use the template instead

**Target audience**: Anyone planning a Carpentries-style workshop (Software, Data, Library Carpentry) who has a basic GitHub account.

**Prerequisites**:
- A free GitHub account (sign up at github.com if you don't have one)
- A web browser
- (Optional but recommended) Basic familiarity with Markdown

---

## Why Use The Carpentries Workshop Template?

The Carpentries provides a ready-made template that:

- Looks professional and consistent with hundreds of Carpentries workshops
- Automatically generates schedule, setup, FAQ, and other standard pages
- Is mobile-friendly
- Is hosted for free via **GitHub Pages**
- Supports easy customization via one main file (`_config.yml`)

There are two main Carpentries website types:

- **Workshop websites** → short-term event pages (what this guide covers)
- **Lesson websites** → long-term curriculum pages (uses The Carpentries Workbench — see notes at end)

---

## Step 1: Create Your Repository from the Template

**Important**: Do **NOT** fork the repository — use GitHub's "Use this template" feature instead.

1. Go to:  
   https://github.com/carpentries/workshop-template

2. Click the green **Use this template** button (top right) → **Create a new repository**

3. Fill in the details:
   - **Owner**: your GitHub username or an organization
   - **Repository name**: Use the Carpentries naming convention:  
     `YYYY-MM-DD-sitename-lessonname`  
     Example: `2026-05-15-purdue-python-novice`
   - Description (optional): "Python for Beginners – May 2026, Purdue University"
   - Visibility: **Public** (required for GitHub Pages)

4. Click **Create repository**

> **Tip**: If you forget the naming convention, your site will still work — but using the slug format helps The Carpentries index your workshop.

---

## Step 2: Install GitHub Desktop.

1. After installation, login to the application. 

2. Click on `File` then `Clone Repository` on the top left. 

3. Find the newly created repository and save it locally on your desktop. 

4. Go the folder which has the cloned repository. 

5. Any change you make in this folder will reflect on the GitHub desktop application. Make sure to **save** the changes.

6. After making the changes, add a summary (this is required), and then `Push` on the top right of the application. 

That's it! Now you can make changes locally to your webpage without having to open GitHub in a browser.  

**Tip:** If you happen to make changes to the webpage repository from a browser and to make sure you have saved the progress locally in your desktop, all you have to do is `Fetch Origin` in the top right of the application to update your local folder repo of the changes. 


## Step 3: Enable GitHub Pages  - Create another repository 

1. In this second newly created GitHub repository, you will display whatever content you add to the repo you created in Step 1. 

2. For License choose `GNU General Public License` if you wish. 

3. Visibility can be changed at anytime but you can choose either to keep it `Public` or `Private`. 

4. In this repository, create and open the file called `_config.yml`

5. Add [Title], [Description] for the `_config.yml` if you want to. 

6. Create a file called `index.html` or whatever name you prefer. This will be the place where you make changes to your webpage. You will need to learn html coding here! Check this [out](https://www.w3schools.com/html/html_intro.asp). 

7. In our case, we have a repository/webpage name called `spatialturn.github.io`. See [here](https://github.com/SpatialTurn). See the changes we made there!

8. ** Alternatively, you can also use the template we created [here](https://github.com/SpatialTurn/carpentrytemp.github.io) and create your very own html repo.**

---

## Step 4: Adding Content to Webpage. 


1. Open the folder called episodes in repository created using the carpentry template in Step 1. 

2. You should see a file called `introduction.md`. 

3. This is the file where you can add content for a specific module. 

4. You can always add newer modules by adding newer .md or markdown files within the episodes folder. 

5. Make sure to add that particular file name in `config.yaml` file and save it. It is usually around line 67.  

6. By default `config.yaml` has only `introduction.md` but you can more to that if you decide to add more content to it. 

7. Check the changes we made when we created our webpages for the Data Analysis module [here](https://github.com/SpatialTurn/DataAnalysis).  

**Tip:** See the changes we made to `episodes` folder and `config.yaml` file. 

