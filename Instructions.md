# Backstory

Imagine you are working on a recipe application. You and your team are responsible for updating the cake recipes. Some of you are responsible for changing the `ingredients` and others are responsible for changing the `instructions`.

# Dev Tasks

During your workweek, your team will receive some requests to update a Brazilian Carrot Cake recipe (in this same file, below). Follow the next steps to make those changes.

I will simulate working with two different people `Ana` and `Banana`.

## Check Setup

Before you start, make sure you followed the instructions in README.md.

After following those steps, let's get started with checking your environment.

Open Git Bash or native shell and navigate to the project directory (use `cd` to navigate).

Once there, you should see something like this:

In `blue` is your current branch, which should be `main` for everyone for now.

## First change - working with branches

It's very rare that teams will develop directly in the `main` branch. A common practice is to create another branch to implement new features and then later merge that branch into `main`.

You can have multiple branches at a time! Here we will use a naming convention `yourname/feature-name`.

### Task 1:

**Ana - Update the carrot quantity from 3 to 4.**

Make sure you are in the main branch. If note, run this command:\
`git checkout main`

Before you begin your work, use the `pull` command to get the most updated version of main:\
`git pull origin main`

Create a new dev branch and check it out:\
`git checkout -b ana/update-carrot-qty`

The `blue` branch name should now be `ana/update-carrot-qty`.\
Update line FIXME: from 3 to 4 and save your changes.\
Now you are ready to make a commit. Let's check our changes:\
`git status`

You should see your file in `green` because it was changed. Say you changed more files, but they don't belong in this current commit. Using `git status` helps you see if you may have changed something accidentally.\
Another helpful command is:\
`git diff <file name>`

This will show all changed in the specified file. For now, let's continue with commiting the current changes.\
First, stage your files:\
`git add <file name>`\
Then commit the staged files with a message:\
`git commit -m "Updated carrot quantity from 3 to 4"`

Now let's push our changes to our remote repo:\
`git push origin ana/update-carrot-qty`

Done!

**Banana - Update the baking dish size from 9x13 to 9x12.**

Make sure you are in the main branch. If note, run this command:\
`git checkout main`

Before you begin your work, use the `pull` command to get the most updated version of main:\
`git pull origin main`

Create a new dev branch and check it out:\
`git checkout -b banana/update-dish-size`

The `blue` branch name should now be `banana/update-dish-size`.\
Update line FIXME: from 3 to 4 and save your changes.\
Now you are ready to make a commit. Let's check our changes:\
`git status`

You should see your file in `green` because it was changed. Say you changed more files, but they don't belong in this current commit. Using `git status` helps you see if you may have changed something accidentally.\
Another helpful command is:\
`git diff <file name>`

This will show all changed in the specified file. For now, let's continue with commiting the current changes.\
First, stage your files:\
`git add <file name>`\
Then commit the staged files with a message:\
`git commit -m "Updated baking dish size from 9x13 to 9x12"`

Now let's push our changes to our remote repo:\
`git push origin banana/update-dish-size`

Done!

### Task 2:

**Both - rebase and merge with main**

Now that your changes were reviewed and approved, let's merge them with main.\
Checkout main and pull the most current changes:\
`git checkout main`\
`git pull origin main`

Checkout your branch and rebase with main:\
`git checkout <your-branch>`\
`git rebase -i main`\
This will open the editor to show all the commits in your branch. For now, we don't have to do anything. Just type `:q` + `enter`.

Push your changes to your remote branch - this will be helpful when working with `Merge Requests`.\
`git push -f origin <your-branch>`

We need the flag `-f` (force) because there were changes to the local repository that should override the remote repo.

Now chekout `main` again and merge.\
`git checkout main`\
`git merge <your-branch>`\
And push your changes to the remote repo:\
`git push origin main`

This probably changes based on the company standards, but it's good practice to clean up your branches after you are done using them.\
`git push origin :<your-branch> # deletes remote branch`\
`git branch -d <your-branch> # deletes local branch`

## Second change - handling merge conflicts

// TODO: add steps
