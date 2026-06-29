---
title: "Building Your Own Carpentries Lesson"
teaching: 50
exercises: 25
---

:::::::::::::::::::::::::::::::::::::: questions

- What is Markdown and how do I use it to write lesson content?
- How do I create a Carpentries-style lesson website using the Workbench template?
- How do I add and organize episodes in my lesson?
- How do I work on my lesson locally using GitHub Desktop?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Write formatted text, headings, lists, links, and images using Markdown
- Create a Carpentries lesson repository from the official template
- Clone the repository locally using GitHub Desktop
- Add episodes and configure the lesson structure
- Understand the Carpentries Workbench file layout

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

This morning you designed a geospatial teaching module — you identified a spatial problem, the data it requires, and where to find that data. Now you will build it as a Carpentries-style lesson website, hosted for free on GitHub Pages.

We will start with Markdown basics (the language Carpentries lessons are written in), then walk through creating and customizing a lesson repository.

**Prerequisites:**

- A free [GitHub account](https://github.com/join)
- A web browser
- [GitHub Desktop](https://desktop.github.com/) installed

---

## Part 1: Markdown Basics

All Carpentries lesson content is written in **Markdown** — a lightweight text format that converts to HTML automatically. You do not need to know HTML. Markdown is designed to be readable as plain text and simple to learn.

### Headings

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

Use headings to structure your episodes into sections. In Carpentries lessons, `##` is the standard section heading.

### Text Formatting

```markdown
**Bold text**
*Italic text*
`Inline code`
```

### Links and Images

```markdown
[Link text](https://example.com)

![Alt text describing the image](image.png "Optional title")
```
**Note:** The image has to be in the same folder where your episodes/modules exist. More on the episodes folder below. 

### Lists

```markdown
Bulleted list:
- Item one
- Item two
- Item three

Numbered list:
1. First step
2. Second step
3. Third step
```

### Code Blocks

Use triple backticks with an optional language name for syntax highlighting:

````markdown
```python
import pandas as pd
df = pd.read_csv("data.csv")
```
````

### Tables

```markdown
| Column A | Column B | Column C |
|----------|----------|----------|
| Row 1    | Data     | Data     |
| Row 2    | Data     | Data     |
```

### Carpentries-Specific Blocks

The Carpentries Workbench adds special fenced blocks for pedagogical elements:

```markdown
::::::::::::::::::::::::::::::::::::: callout

### Tip
This is a callout box for important notes or tips.

::::::::::::::::::::::::::::::::::::::::::::::::
```

```markdown
:::::::::::::::::::::::::::::::::::: challenge

### Exercise Title
Write the exercise prompt here.

::::::::::::::::::::::::::::::::::::::::::::::::
```

```markdown
::::::::::::::::::::::::::::::::::::: keypoints

- First key takeaway
- Second key takeaway

::::::::::::::::::::::::::::::::::::::::::::::::
```

Other available block types include `questions`, `objectives`, `discussion`, and `solution`.

::::::::::::::::::::::::::::::::::::: callout

### Quick Reference

For a full Markdown guide, see [markdownguide.org](https://www.markdownguide.org/basic-syntax/). For Carpentries-specific formatting, see the [Workbench documentation](https://carpentries.github.io/sandpaper-docs/).

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Part 2: Create Your Lesson Repository

The Carpentries provides an official template called the **Workbench** that generates a professional lesson website automatically from your Markdown files. You do not need to write any HTML or CSS.

### Step 1: Use the Template

**Important:** Do **not** fork the repository — use GitHub's "Use this template" feature instead.

1. Go to the Carpentries Workbench template:
   [https://github.com/carpentries/workbench-template-md](https://github.com/carpentries/workbench-template-md)

2. Click the green **Use this template** button (top right) → **Create a new repository**

3. Fill in the details:
   - **Owner:** your GitHub username or organization
   - **Repository name:** use the Carpentries naming convention — `YYYY-MM-DD-sitename-topicname`
     (e.g., `2026-06-30-purdue-geospatial`)
   - Keep **Include all the branches** on 
   - **Visibility:** **Public** (required for GitHub Pages to work)

4. Click **Create repository**

Your lesson website will be built automatically and available at:
`https://yourusername.github.io/your-repo-name/`

In this case:

1. `yourusername` - This is your *GitHub username*. 
2. `your-repo-name` - This is your repo name. From the example above **2026-06-30-purdue-geospatial**.

It may take a couple of minutes for the first build to complete.

::::::::::::::::::::::::::::::::::::: callout

### Tip

If you forget the naming convention, your site will still work — but using the `YYYY-MM-DD-sitename` format helps The Carpentries community index and discover your workshop.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Part 3: Work Locally with GitHub Desktop

Editing files directly on GitHub works for small changes, but for building a full lesson it is much easier to work locally on your computer. GitHub Desktop lets you do this without using the command line.

### Step 1: Clone Your Repository

1. Open **GitHub Desktop** and log in with your GitHub account.
2. Click **File → Clone Repository**.
3. Find the lesson repository you just created and choose a local path (e.g., your Desktop).
4. Click **Clone**.

You now have a local folder with all the lesson files. Any changes you make to files in this folder will appear in GitHub Desktop.

### Step 2: Edit, Commit, and Push

The workflow is:

1. **Edit** files in your local folder using any text editor (VS Code, Notepad++, or even plain Notepad)
2. **Save** the files
3. Open **GitHub Desktop** — you will see your changes listed
4. Write a short **summary** describing what you changed (this is required)
5. Click **Commit to main**
6. Click **Push origin** in the top right to send your changes to GitHub

Your lesson website will rebuild automatically after each push.

### Staying in Sync

If you make changes on GitHub through a browser (or a collaborator pushes changes), click **Fetch origin** in GitHub Desktop before editing locally. This pulls the latest version so you do not create conflicts.

---

## Part 4: Understanding the Lesson Structure

Your cloned folder contains several important files and folders:

```
your-lesson/
├── config.yaml          ← lesson title, description, episode order
├── episodes/
│   └── introduction.md  ← your first episode (lesson page)
├── instructors/         ← instructor-only notes
├── learners/
│   └── setup.md         ← setup instructions for students
└── profiles/            ← learner profiles
```

### The `config.yaml` File

This file controls your lesson's title, description, and the order in which episodes appear. Open it in a text editor and look for the `episodes` section (around line 67):

```yaml
episodes:
- introduction.md
```

To add more episodes, list them here in the order you want them to appear:

```yaml
episodes:
- introduction.md
- data-collection.md
- analysis.md
- visualization.md
```

### The `episodes/` Folder

Each `.md` file in this folder becomes one page (episode) in your lesson website. The file you worked with throughout this workshop — with its YAML header, questions, objectives, content, and keypoints — is exactly what goes here.

### The `learners/setup.md` File

This is where setup instructions for students go — software to install, accounts to create, and data to download. The setup page we built on Day 1 of this workshop is an example of this file.

---

## Part 5: Add Your First Episode

Now you will turn the geospatial module you designed this morning into a Carpentries episode.

### Step 1: Create the File

In your local `episodes/` folder, create a new file with a descriptive name (e.g., `urban-heat-analysis.md`). Start with the standard Carpentries header:

```markdown
---
title: "Your Episode Title"
teaching: 30
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions

- First question your episode addresses
- Second question

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- First learning objective
- Second learning objective

::::::::::::::::::::::::::::::::::::::::::::::::

## Section 1

Your content here — explanations, instructions, code blocks, images.

:::::::::::::::::::::::::::::::::::: challenge

### Exercise Title

Exercise instructions here.

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- First key takeaway
- Second key takeaway

::::::::::::::::::::::::::::::::::::::::::::::::
```

### Step 2: Register It in `config.yaml`

Open `config.yaml` and add your new file name to the `episodes` list:

```yaml
episodes:
- introduction.md
- urban-heat-analysis.md
```

### Step 3: Commit and Push

1. Save both files
2. In GitHub Desktop, write a commit summary (e.g., "Add urban heat episode")
3. Click **Commit to main**, then **Push origin**
4. Wait a few minutes, then check your lesson website — your new episode should appear in the navigation

:::::::::::::::::::::::::::::::::::: challenge

### Exercise: Build Your Module

Using the geospatial teaching element you designed this morning, create a Carpentries episode:

1. Create a new `.md` file in your `episodes/` folder
2. Add the YAML header with title, teaching time, and exercise time
3. Write at least a `questions` block, an `objectives` block, one content section with a heading, and a `keypoints` block
4. Add the file to `config.yaml`
5. Commit and push
6. Verify that your episode appears on your lesson website

If time allows, add a second section, an exercise block, or a callout.

::::::::::::::::::::::::::::::::::::::::::::::::

---

## Reference: Example Lesson Repository

To see a completed example of a multi-episode Carpentries lesson built using this workflow, see the Data Analysis module we created: [github.com/SpatialTurn/DataAnalysis](https://github.com/SpatialTurn/DataAnalysis). Pay attention to the `episodes/` folder and the `config.yaml` file to see how episodes are organized.

You can also use the template we created at [github.com/SpatialTurn/carpentrytemp.github.io](https://github.com/SpatialTurn/carpentrytemp.github.io) as a starting point for a custom landing page for your workshop.

---

::::::::::::::::::::::::::::::::::::: keypoints

- Markdown is the language used to write Carpentries lesson content — it is plain text with simple formatting rules.
- The Carpentries Workbench template generates a professional lesson website automatically from your Markdown files.
- Each episode is a single `.md` file in the `episodes/` folder; the `config.yaml` file controls which episodes appear and in what order.
- GitHub Desktop lets you edit lesson files locally and push changes without using the command line.

::::::::::::::::::::::::::::::::::::::::::::::::