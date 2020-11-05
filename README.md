# Hugo Starter Blog
Welcome to the start of your own static site! With the power of [Hugo's](https://gohugo.io) blazing fast framework for creating websites, you can focus on what matters most: content!  

Fork this repository, pick your favorite name for it and let's get started!

## What you will need

- GitHub Account (of course!)
- [Gitpod.io Account](https://gitpod.io) (Don't worry, it's free for public repos for 50 hours/month which is plenty)

## What the end result should look like 
![Website Screenshot](website.png)   

## A Note before we dive in
This setup only needs to happen once. After that, you can even create new posts on your phone from the GitHub app if you are handy with markdown. Several things are taken care of so that you can get up and running quicker:
- The repository includes a GitHub action to automatically deploy your website each time you commit a change
- Gitpod is used so you do not need to install any software on your machine
- There's this handy document to help you along the way   

Let's get started!
---   

## Setup Checklist
To help you keep track of where you are, follow along with this checklist (sorry you can't just click these boxes, but check each of these off in your head):

- [x] [Discover water on the Moon](https://www.usatoday.com/story/news/nation/2020/10/26/nasa-announce-an-exciting-new-discovery-moon-monday/6039412002/)
- [ ] [Fork this repository](#task-0-access)
- [ ] [Create a new public GitHub repository with the name **YourUsername.github.io** and initialize with a README](#task-2-new-repo)
- [ ] [Generate a Personal Access Token with admin:repo_hook, repo, workflow privileges](#task-3-personal-access-token)
- [ ] [Set the GitHub Secrets for *TOKEN*, *USERNAME* and *GHPAGESREPO*](#task-4-setting-the-secrets)
- [ ] [Give Gitpod GH Write access](#task-5-set-gitpod-access-controls)
- [ ] [Open the repository in Gitpod](#task-6-launch-gitpod)
- [ ] [Modify the config.toml from Gitpod](#task-7-modify-the-hugo-config)
- [ ] [Change the theme from Gitpod](#task-8-change-the-theme)
- [ ] [Add your first post from Gitpod!](#final-task-add-you-first-post)

### Task 0: Access
Of course, make sure you are logged in to GitHub and have logged in to [Gitpod](https://gitpod.io) at this point.   
   
### Task 1: Forking
Easy! Just click the little *Fork* button on the top right of this repository.   

### Task 2: New Repo
Click the *+* symbol on the top-right navigation bar and select *New repository*.  
- Make sure the repository name is **YourUsername.github.io** (obviously use your own username) or this won't work  
- Add a description if you want  
- Check the box on the bottom to add a README file  

### Task 3: Personal Access Token
Go to [https://github.com/settings/tokens](https://github.com/settings/tokens) and select *Generate new token*
- Give it a memorable Note like "Github Actions Token"   
- Select the high-level scopes of "repo", "admin:repo_hook", and "workflow"   
- Click *Generate Token* and save the token somewhere safe. GitHub will keep it hidden forever once you leave this page.   

### Task 4: Setting the Secrets
You don't want to worry about building the code for your website and then deploying it each time you make a change right? This repo comes with a GitHub action to automatically publish to the repo you created in task 1. You just have to set the secrets in this forked repo:   
- Make sure you are in YOUR repo where this README file lives
- Click on Settings
- Click on Secrets
- *New Secret* -> USERNAME (type in your GitHub username)
- *New Secret* -> GHPAGESREPO (type in the repository you created in Task 2 e.g., AstroTester.github.io)
- *New Secret* -> TOKEN (paste in the Personal Access Token from Task 3)
- Click on the Code tab to return to the repository

### Task 5: Set Gitpod Access Controls
This will grant GitHub write permissions to Gitpod which you will need if you want to easily make website changes from your browser.  
- Go to [gitpod.io/access-control](https://gitpod.io/access-control)
- In the GitHub area, check *write public repos* and *update workflows*
- Click update and grant access

### Task 6: Launch Gitpod
Back to the repository. 
- Go to the URL portion of your browser and modify the URL to insert <u>gitpod.io/#</u> just before the word GitHub.
- It should now look something like: https://gitpod.io/#github.com/AstroTester/hugo-starter-blog
- Go to that link which will open a new Gitpod instance

### Task 7: Modify the Hugo Config
From Gitpod, find the config.toml file and click it. Replace the following values and make sure to preserve double quotes where they exist:
- baseURL: replace the value with https:// + your repository name from Task 2 e.g., baseURL: "https://AstroTester.github.io"
- title: set a title for your website
- author -> name: Type in your name!
- languages -> languages.en -> title: Type in your title again
- languages -> languages.en -> subtitle: Type in a witty subtitle

When you are done, click on the *Source Control* button on the left (looks like a Y under the magnifying glass).
- Hover over the word *Changes* and click the + symbol
- In the *Message* field add a short summary of the changes you just made. e.g., "Customized my config"
- Click the *Checkmark* above the message field to save your changes
- Click on the *Synchronize* button at the very bottom to push your changes to the server. Here is what that button looks like:   
![Git Sync](synchronize.png)
- Wait a minute or two and then check out your website. If you did everything right, you should now be able to access your own website at https://YourUsername.github.io

### Task 8: Change the Theme
Optional but recommended. Your website theme should be an extension of your creativity. Thankfully, you only have to choose a theme once and there are hundreds to choose from.  
- Go to [themes.gohugo.io](https://themes.gohugo.io) and click on the *Blog* category
- Find a theme that speaks to you and open it in a new tab
- Look at the setup instructions for that theme. If it has an instruction with `git submodule add` then you found a good one to add. Copy that whole line.
- (Keep the theme instructions open in a separate tab, you will come back to this in a second)
- Open your repository in Gitpod again
- Paste in the `git submodule add` command into the terminal window at the bottom and press enter
- Open the config.toml file and change the value for *Theme* to the new theme name you added
- From the terminal, type in `hugo server` which will open your website with the theme changes
  - Make sure everything looks correct and type `Ctrl+C` to stop the website
- Click on the *Source Control* icon, add the new changes, save with a commit message, and synchronize your changes with the server

### Final Task: Add you first post!
Now for the fun part and really the only part you need to remember once you are done :)   

- First, reopen the repository in Gitpod.  
- Next, type in the Hugo command in the terminal to create a new post in content/posts: `hugo new posts/first-blog-post.md`

> Taking a look at this command: `hugo new` will create a new file in the path you give it.  
> - The new file will live in the content folder  
> 
> `posts` puts your new post in the content -> posts folder which is a good idea so that your posts are all together.
> `first-blog-post.md` gives your post a name. Note, you must include the .md extension so that Hugo knows it is a Markdown file.

Next, go ahead and fire up the hugo server again so that you can see your edits in realtime. From the terminal execute `hugo server`.

Now, find and open your new blog post in the editor. Using [Markdown syntax](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf), write your post.
You can view your post changes in the web editor to make sure that the formatting is correct.
If you want the post to be live on the website, change the "draft" flag on the file to false and commit the change.
That's it, you just published your first blog post! The world is your oyster and all that jazz.