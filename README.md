# Purpose

## Old Solution:
I have been experimenting with Test Driven Development and working with libraries that I am 
unfamiliar with.  My first approach was to delete revisions.  However, I do not like this solution
since I have to add the test that already written back in the code.  

## New Solution

<ol>
    <li>Create a Github Repository</li>
    <li>For each new test do the following</li>
    <ol>
        <li>Create a branch from the previous branch</li>
        <li> write the failing test and make it pass and refactor</li>
        <li> Using Git commit and push the modifications</li>
    </ol>
</ol>

### What happens if a mistake is made in the previous branch
<ol>
    <li>Checkout the branch that contain the original code have the error</li>
    <li>Fit the bug and do the add/commit/push</li>
    <li>Use a script to execute <code>git pull</code> on all the branches </li>
</ol>

Using .gitignore is very useful since it removes files from git status that will never be tracked 
and make the display easier to read.

git branch -M main -- -M is a short cut for move or force.
Without this command the code is not on the right branch.  Even
though there is main branch in the local repository it does not seem
to be the correct branch.  I have skipped this command twice and it 
caused problems.

## Experiments

In GitHub create the repository : experiment_git_for_tdd

### Step 1
<code>git init</code><br>
<code>git add README.md</code><br>
<code>Put the .gitignore into the repositories' directory and add it</code><br>
<code>git commit -m "Added rough draft of the experiment documentation"</code><br>

<code>git remote add origin https://github.com/CharlesStockman/experiment_git_for_tdd.git"</code>
<code>git branch -M main</code><br>
<code>git push -u origin master"</code>

### Step 1 -- Create a new branch and merge it without delete the branch

<code>git checkout -b branch_1</code><br>
<code>Create file called file1</code><br>
<code>git add -A </code>
<code>git commit -m "Working on Step 1 Experiment ( See Readme.md )"</code>
<code>git push --set-upstream origin branch_1</code>

#### Step 1a 
<code>git checkout main</code>
<code>git merge branch_1</code>
<code>git merge --no-ff</code>

### Step 2 
<code>git checkout -b branch_2 from branch_1 </code><br>
<code>Create file called file2</code><br>
<code>Using git add/commit/push the changes</code>

### Step 3
<code>git checkout -b branch_3 from branch_2 </code><br>
<code>Create file called file3</code><br>
<code>Using git add/commit/push the changes</code>

### Step 5 -- See if an change from an earlier branch can be merged into a new branch
<code>git checkout branch_1</code>
<code>edit file1<code>
<code>git add file1</b>
<code>git commit -m "Made change to file1"</code>
<code>git push</b>

<code>git checkout branch_2</code>

Verify branch2 has the change for branch1

### Step 5
<code>git checkout branch_1</code><br>
<code>Make a change to the file</file><br>
<code>Use an alias / python program / ansible to do a git pull and push</code>

## Lessons 

### Adding a file to a push repository and not changing the commit message
<ol>
    <li><code>Use git add to add the files</code></li>
    <li><code>git commit -amend --no-edit</code></li>
    <li><code>git push --force</code></li>
</ol>



