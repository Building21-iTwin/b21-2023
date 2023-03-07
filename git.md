# Getting started with GitHub

## What is Git?

A Git repository is a place to store source code that stores the current and all previous versions of each file. Once you save a change it can never be accidentally deleted.

## What is GitHub?

A website that hosts Git Repositories and has other services that developers use to build and maintain their code.

## How to get started?

Go to https://github.com and create an account, it's free!

Share user name so you can be added to the team.

Download this repository using the command:`git clone https://github.com/Building21-iTwin/b21-2023.git`

## How to use GitHub

[GitHub Cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)

Use 'Setup' instructions to configure.

Configure email using private email found here: http://github.com/settings/emails

## Creating your first GitHub repository

You'll create a new repository on GitHub, and then `push` your local code to the repository.
**When you created your app using `npx create-app ...`, a local git repository was created on your machine.**
We're going to push that local repo to Github.

1. Go to https://github.com and login with the account info you created above.
2. Click on the green "Create Repository" (or maybe "New") button to start creating a new repo.
3. Enter a name for your repository. The name you used to create your app is a good idea.
4. Click "Create Repository" at the bottom of the page.
5. Because you already have a local repository, you'll want to follow the second block of instructions titled "…or push an existing repository from the command line"
   - Go to your terminal in VS Code and execute the commands in that code block one-by-one.
   - After that, reload the webpage. You should see your code!

## Manually creating a local git repository

As mentioned above, when you ran `npx create-app` a local git repo was created for you. At some point, you may want to create one yourself. To do so:

1. In a directory which is not already a git repo (you can test if a directory is a git repo by executing `git status`), type `git init`.
2. Thats's it! You'll see output like "Initialized empty Git repository in {folderPath}/.git/"
