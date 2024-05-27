---
layout: ../../layouts/PostLayout.astro
title: "How to Display Latest Blogs GitHub Profile?"
excerpt: "In this post, we dive into Github Actions and how to use it to update our Github Profile's REAME with our latest blogs."
createdAt: "2024-05-27"
author: Zemerik
---

In this post, we will create a Workflow which updates our GitHub Profile with out latest Blogs on dev.to. To do this, you will need:

- A GitHub Account
- A little of passion

## LINKS:

- My GitHub (You can find an example here) - https://github.com/Zemerik/Zemerik
- YouTube Video - https://youtu.be/As7KgTZOrlE
- Source code - https://gist.github.com/Zemerik/ebb6f6af7c64173adf22aab5cd2c68a7
- Support - https://discord.gg/td5xqmzEcg

## 1. SET UP README.MD

- The first step in this process, is to define where we want our blogs. To do that, copy paste the following code in your README.md where you want your blogs:

```
<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
```

> NOTE: Your blogs will be showing in the middle of the two comments. 

## 2. WORKFLOW

- The next step in this process is to create a workflow to update our README. 

- Create a `blog-post-workflow.yml` file in the `.github/workflows/` directory. Ensure your directory has no typo's!

- We now need to write the workflow in the file which we created. Copy paste the code below into that file:

```yml
name: 📚Blogs
on:
  schedule:
    # Runs every hour
    - cron: '0 * * * *'
  workflow_dispatch:

jobs:
  update-readme-with-blog:
    name: ✅Update with latest Blogs
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          max_post_count: "4"
          feed_list: "https://dev.to/feed/YOUR DEV.TO USERNAME HERE"
```

> Remember to add your Dev.to username at the end of the URL on the last line

## 3. ACTIONS SETTINGS:

- Head over to the Settings tap located at the top. 

![Settings Tab](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rmw929mviuz1s9nuawkz.png)

- Navigate your way to `Actions > General` Tab from the left. 


![Actions Settings](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6e22us1yyyl9g0ht9ynb.png)

- Ensure that your settings match the settings below

![Setting 1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cfxv5xqzfm2lsoyl80ef.png)

![Setting 2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gmiv9z6cgx3xfvl27jg3.png)

![Setting](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4d6y4dt8beuscxquvo4u.png)

## 4. EXECUTING:

- Finally, we are ready to run our workflow. To do so, first head over to the `Actions` tab on the top

![Actions Tab](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5agnz6fwgslwdzem7nmi.png)

- Select `📚Blogs` from the menu on the left. 

![Blogs Tab](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yyfxjzjem2hehxqlm1x7.png)

- Click on the `Run workflow` dropdown, and click the `Run workflow` button. 

![Run Workflow](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kn4tmfsjuppky3rv7e8z.png)

### YOUR README SHOULD NOW HAVE BEEN UPDATED WITH YOUR LATEST BLOGS

## SUMMARY:

In this blog, we successfully created and executed a workflow to update our Github Profile's README with our latest blogs on Dev.to. For any kind of support, you can refer to the `Links` section at the top. 

### THANKS FOR READING. HOPEFULLY YOU FOUND THIS BLOG HELPFUL!!!
