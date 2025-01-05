---
title: "Blogging: Setup Free Hosting in 20 Minutes"
categories: [blogging,hosting]
tags: [blogging, jekyll, static-side-generator]     # TAG names should always be lowercase
---

We will setup a blogging web site using jekyll. Jekyll is a static site generator that transforms plain text into beautiful static web sites. We develop in docker using VisualStudio Code dev container. We will create a blog post as a Markdown file(plain text). Jekyll will transform the Markdown file to an HTML page. The web site can be tested locally. To host out blogging web site for free we use GitHub. Alternatively we create a docker image for self hosting.


This setup is for developers. Non-technical people please check {% if page.previous %}[{{ page.previous.title }}]({{ page.previous.url }}){% endif %}

# Fork the Starter Repository
* Login to [github](https://github.com)
* Fork the [starter](https://github.com/cotes2020/chirpy-starter) repository
* Click the "Use this template" button and then select Create a new repository
* Name the new repository <github-username-all-lowercase>.github.io

# Create a VS Code Project
* Clone a forked template Repository (replace the following github URL)
* ```bash
git clone https://github.com/cotes2020/chirpy-starter
```
* In vs code open the project (optional: vs code > File > Save as *.github.io.code-workspace)

# Start our Development Server
* Open the project as dev container
* Run the web site locally. In vs code open a Terminal and run
```bash
bundle exec jekyll s
```
* Test locally <http://127.0.0.1:4000/>



# Create a new blog page
* create a new file _post/2025-01-04-jekyll.md
```md
---
title: Setup a Free Blogging Web Site in 20 Minutes
categories: [blogging]
tags: [jekyll]     # TAG names should always be lowercase
---
We will Setup a Free Blogging Web Site in 20 Minutes.
```
* Test locally <http://127.0.0.1:4000/>



# Modify an existing blog page
* edit the file  _post/2025-01-04-jekyll.md
* after saving vs code will automatically regerate the page (regeneration output is visible in code terminal)
* Test locally by doing a browser refresh

# Commit the blog page to git
fork repo

# Deploy the blog page to GitHub
https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
https://chirpy.cotes.page/posts/getting-started/


GitHub Repository > Settings > click Pages in the left navigation bar > Source="GitHub Actions"
Push a commit to Repository to trigger the Actions workflow  > Actions tab: you should see the workflow Build and Deploy running > the site will be deployed

# Create a Dockerimage for local hosting

# Documentation
jekyll <https://jekyllrb.com/>
jekyll-theme-chirpy <https://github.com/cotes2020/jekyll-theme-chirpy/>
https://chirpy.cotes.page/posts/getting-started/

