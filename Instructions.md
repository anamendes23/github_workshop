# Backstory

Imagine you are working on a recipe application. You and your team are responsible for updating the cake recipes. Some of you are responsible for changing the `ingredients` and others are responsible for changing the `directions`.

# Dev Tasks

During your workweek, your team will receive some requests to update a Brazilian Carrot Cake recipe (in the file copied from Template.md). Follow the next steps to make those changes.

I will simulate working with two different people `Ana` and `Banana`.

## Check Setup

Before you start, make sure you followed the instructions in README.md.

After following those steps, let's get started with checking your environment.

Open Git Bash or native shell and navigate to the project directory (use `cd` to navigate).

Once there, you should see something like this:\
<img src="https://user-images.githubusercontent.com/35348652/175826869-4b648117-6959-443d-8c11-b656dee91087.png" alt="cli" width="600"/> 

In `blue` is your current branch, which should be `main` for everyone for now.

## First change - working with branches

It's very rare that teams will develop directly in the `main` branch. A common practice is to create another branch to implement new features and then later merge that branch into `main`.

You can have multiple branches at a time! Here we will use a naming convention `yourname/feature-name`.

### Task 1 - implement changes:

If you are working with a teammate, each of you should do a separate change to avoid merge conflict.\
If you are working by yourself, try both tasks to see how it works to have multiple branches at a time.

**Ana - Update the carrot quantity from 3 to 4.**

Make sure you are in the main branch. If not, run this command:\
`git checkout main`

Before you begin your work, use the `pull` command to get the most updated version of main:\
`git pull origin main`

Create a new dev branch and check it out:\
`git checkout -b ana/update-carrot-qty`

The `blue` branch name should now be `ana/update-carrot-qty`.\
Update `line 11` from 3 to 4 and save your changes.

Now you are ready to make a commit. Let's check our changes:\
`git status`

You should see your file in `red` because that file was changed, but changes are not staged yet. Say you changed more files, but they don't belong in this current commit. Using `git status` helps you see if you may have changed something accidentally.\
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
Update `line 25` from 9x13 to 9x12 and save your changes.\
Now you are ready to make a commit. Let's check our changes:\
`git status`

You should see your file in `red` because that file was changed, but changes are not staged yet. Say you changed more files, but they don't belong in this current commit. Using `git status` helps you see if you may have changed something accidentally.\
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

### Task 2 - merge changes to main:

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

Merge conflicts happen often. There are a few good practices to help with that:

* Keep your changes as small as possible
    - when implementing a feature, try to break things down to make changes of components that work together. That will help during code review and it'll reduce the chances of a merge conflict - and when it happens, it'll be a lot easier to fix.

* Rebase/sync with main frequently
    - as you make your changes, other developers are merging changes to main. If you frequently rebase your branch with main, you will have the most recent code and will have an easier time merging your changes later.

Now let's simulate a merge conflict and learn how to resolve it.

### Task 3 - fix typo

Two branches will fix the same line, but they will write different things. Practice with a friend or do both changes but in different brances.

**Both - before beginning**

Make sure you have the most recent version of main before you begin. Everyone should run the command:\
`git checkout main # run this if you are not in main`\
`git pull origin main`

**Ana - Update and merge first**

Create a new dev branch and check it out:\
`git checkout -b ana/fix-typo`

The `blue` branch name should now be `ana/fix-typo`.\
Update `line 15` with:\
`- 2 cups all-purpose white flour`

Now you are ready to make a commit. Let's check our changes:\
`git status`

First, stage your files:\
`git add <file name>`\
Then commit the staged files with a message:\
`git commit -m "Fixed typo and added flour type"`

Now let's push our changes to our remote repo:\
`git push origin ana/fix-typo`

Let's say Kitty approved your changes, so rebase with main and merge:\
`git checkout main`\
`git pull origin main`\
`git checkout <your-branch>`\
`git rebase -i main`\
`git push -f origin <your-branch>`\
`git checkout main`\
`git merge <your-branch>`\
`git push origin main`\

Clean up your branch:\
`git push origin :<your-branch> # deletes remote branch`\
`git branch -d <your-branch> # deletes local branch`

Done!

**Banana - Update merge second. Will handle merge conflict**

Create a new dev branch and check it out:\
`git checkout -b banana/fix-typo`

The `blue` branch name should now be `banana/fix-typo`.\
Update `line 15` with:\
`- 1 1/2 cups all-purpose flour (white or whole)`

Now you are ready to make a commit. Let's check our changes:\
`git status`

First, stage your files:\
`git add <file name>`\
Then commit the staged files with a message:\
`git commit -m "FIxed typo, updated quantity and added flour type"`

Now let's push our changes to our remote repo:\
`git push origin <your-branch>`

Let's say Kitty approved your changes, so you start the merge process:\
`git checkout main`\
`git pull origin main`\
`git checkout <your-branch>`\
Now when you rebase, you will get a merge conflict:\
`git rebase -i main`\
Git provides a few instructions on how to solve the issue.\
You can stop rebasing by running:\
`git rebase --abort`\
Or you can resolve the conflicts and continue. You will see a list of files that have conflict. In this case, open your file in your prefered editor (I'm using vs code) and you should see the conflict areas in the file.\
If you are not using an IDE, which will mark the conflict areas for you, search for `<<<<<<< HEAD` and you will find the beginning of the area where the merge occurs.\
When you find your conflict, you have to decide what change is acceptable. If the changes make the code behave differently, resolve with your team. If the conflict is on simple syntax or implementation order, use your judgment to fix it.

Once fixed, you can commit your change and continue rebasing:\
`git status`\
`git add .`\
`git rebase --continue`

Now that the rebase is completed, you have to update the remote repo:\
`git push -f origin <your-branch>`\

We can now finish merging with main:\
`git checkout main`\
`git merge <your-branch>`\
`git push origin main`

Clean up your branch:\
`git push origin :<your-branch> # deletes remote branch`\
`git branch -d <your-branch> # deletes local branch`

Done!

### Note

When your branch has multiple commits, each commit that has a merge conflict has to be resolved when rebasing.\
That's why it's important to have few commits being merged to main at a time. Trust me, it will get very messy when each of your 10+ commits conflict when rebasing - been there.

## Clean up

After completing the tutorial, make sure to delete all your branches and new files. The repo should contain only:

- Instructions.md
- LICENSE
- README.md
- Template.md

Thanks!
