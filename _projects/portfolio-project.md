---
title: "Portfolio Project"
date: 2025-11-4
exercpt: "Project description"
header:
    overlay_image: /assets/images/projects/jekyll_logo.jpg
    teaser: /assets/images/projects/homepage.jpg
    overlay_filter: 0.25
    caption: "Image credit: Matthias Lischka"
    show_overlay_excerpt: false
layout: single
#    overlay_image:
#    teaser: 
# ![Jonah Saitz Engineering Portfolio Home Page](/assets/images/projects/homepage.jpg)
---
# Building My Engineering Portfolio with **Jekyll** and **GitHub Pages**

### 1. **Introduction**

Over the past weekend, I built this site using GitHub Pages and Jekyll, a static site generator (SSG). My goal was simple: create a professional, navigable, 100% free platform to showcase my projects, technical skills, and creative thinking. 

What started as a straightforward task became an opportunity for me to learn about site structure, theme customization, and deployment workflows, and Git for version control. In this post, I'll walk through design decisions, challenges, and lessons learned along the way.

### 2. **Choosing the Tools & Stack**

I wanted a portfolio that was lightweight, customizable, low-maintenance, and free to host. In short, a stack that would give me full control without unnecessary complexity:

* **Jekyll** - A static site generator (SSG) that converts Markdown and HTML templates into a fast, fully functional website. Its simplicity and version-controlled workflow make it ideal for a portfolio. 

* **Minimal Mistakes** - A Jekyll theme designed for clarity and professionalism. Built-in layouts and styling options let me focus on content instead of reinventing the wheel.

* **Git & GitHub Pages** – Git keeps a record of every change, making experimentation safe. GitHub Pages handles free, continuous deployment straight from the repository.

This combination allowed me to test locally, iterate quickly, deploy confidently, and customize freely. More importantly, it reinforced a core part of my engineering philosophy: choose tools that solve the problem efficiently without adding unnecessary overhead. 

<figure>
  <img src="/assets/images/projects/sample_mm.jpg" alt="Sample Minimal Mistakes webpage">
  <figcaption>Figure 1: Sample Minimal Mistakes webpage.</figcaption>
</figure>

### 3. **Setting Up the Environment**

Creating a site with Jekyll and GitHub Pages is straightforward, but not exactly "plug and play." I followed a few important setup steps to get my page up and running:

1. **Fork the Minimal Mistakes repository on GitHub** -> I started by forking [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) then renaming the fork to match my desired GitHub Pages URL (`saitzjonah.github.io`), which automatically creates a site-ready repository. 

2. **Confirm the publishing source** -> In my `saitzjonah.github.io` repository, I navigated to **Settings -> Pages** and selected the branch (`master`) as the publishing source.  GitHub Pages then built and deployed my site from that branch. 

3. **Clone the repository locally** -> With the fork created on GitHub, I cloned the repository to my local machine and navigated to my new directory. This gave me a full local copy of the site where I could experiment with layouts and content without affecting the live version.

4. **Install Ruby and project dependencies** -> As of 2025, Jekyll requires Ruby version 2.7.0 or higher, but the system Ruby on my Mac was outdated (`ruby 2.6.10p210`). The [official Jekyll documentation](https://jekyllrb.com/docs/installation/macos/) recommends the following setup:
	* Install `chruby` and the latest ruby with ruby-install.
	* Configure your shell to automatically use `chruby` (so that it doesn't default to system Ruby).

With the correct Ruby version active, I installed all required gems for Jekyll and the Minimal Mistakes theme in the project directory. Finally, I started a local development server. This compiled the site and served it at `http://localhost:4000`, allowing me to safely iterate on layouts, content, and configuration before pushing changes to GitHub.

5.  **Commit and push changes to GitHub** -> After editing content or layouts locally, I used Git to track and commit my changes. GitHub Pages then automatically builds and deploys the updated site from the master branch. Using version control gave me confidence to experiment locally without worrying about breaking the live site. 

### 4. **Customization & Design Process**

The main reasons I chose Jekyll was its ease of customization. I loaded my `saitzjonah.github.io` directory into VS Code and got started.

I settled on a straightforward, browsing-friendly layout:
* **Home** -> A landing page to introduce who I am, what I do, and display samples of my recent work. 
* **Projects** -> A long-form showcase of all my engineering projects, organized from newest to oldest, with links to full project write-ups, like the one you're reading right now!
* **About** -> A deeper dive into my background, skills, and approach to engineering
* **Contact** -> A clean space for interested people to reach out.
* **Site-wide search bar** -> To let any visitor quickly find relevant content (especially useful as Projects page grows).
* **Footer and side bar** -> For easy-to-access contact info on any page.

With the structure decided, I moved into the code. I used Jekyll's layouts, includes, and front-matter features to create reusable templates and consistent styling across the site. My goal was for the site to look nice and communicate my work clearly, without any major bugs.

<figure>
  <img src="/assets/images/projects/project_page.jpg" alt="Projects on the 'Projects' page displayed in a grid">
  <figcaption>Figure 2: Projects on the 'Projects' page displayed in a grid.</figcaption>
</figure>

### 5. **Challenges & Learning**

Working on this site wasn't without bumps, and each challenge I encountered taught me something valuable. 

* **Learning curve of Jekyll/Minimal Mistakes** -> I'd never worked extensively with GitHub or Jekyll before this project. Learning new software means reading lots of documentation, but fortunately, GitHub, Jekyll, and Minimal Mistakes are all well documented. 
* **Hunting down hidden includes** -> The Minimal Mistakes theme abstracts a lot of its structure into modular includes and remote scripts. What looks like a simple HTML element is often generated through multiple layers of Liquid templates and data files, each referencing another piece somewhere else in the directory tree. This forced me to slow down, trace the logic, and learn how Jekyll builds pages behind the scenes--an exercise in patience and understanding abstraction, not just editing code. 
* **Optimizing AI workflow** -> Tools like Perplexity AI and ChatGPT are remarkable pieces of software, but they also have limitations. For super-specific fixes in HTML and CSS, I observed an increase in hallucinations--like suggestions to modify attributes that didn't exist. In those cases, consulting the official documentation or inspecting the code directly was faster and more reliable.

None of these were major roadblocks, but they reinforced a central principle in the engineer's handbook: building something yourself, even something as simple as a static site, always teaches you more than reading about it. 

<figure>
  <img src="/assets/images/projects/mm_documentation.jpg" alt="Minimal Mistakes documentation page">
  <figcaption>Figure 3: The official Minimal Mistakes documentation page.</figcaption>
</figure>

### 6. **Future Updates**

This site will evolve as my work does. It'll serve as a running log of my engineering projects, both the polished and the half-broken ones. I'm excited to publish new projects in the coming weeks and months! 

### 7. **Useful Links**

* [Minimal Mistakes template on GitHub](https://github.com/mmistakes/minimal-mistakes/)
* [Jekyll installation guide](https://jekyllrb.com/docs/installation/)
* [Minimal Mistakes quick-start guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
* [Basic Markdown syntax](https://www.markdownguide.org/basic-syntax/)