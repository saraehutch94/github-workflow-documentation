# GitHub Workflow

### Here is a step-by-step guide on how to collaborate with other developers on the same project via GitHub

<br>

**Two roles of participants:**

1.) `GitHub manager` --> one person who oversees all push requests to the main master branch; resolves any possible merge conflicts (can also have the role of `developer`)  
2.) `Developers` --> people who are contributing to the main master branch of the project

---

<br>

### **GitHub manager** steps:

1.) Create directory on their computer (where projects are stored) and initialize a git repository in it:

`mkdir <project-name>`  
`cd <project-name>`  
`git init`  
`git remote add origin <remote-repo-link>`  
`git remote -v` \* checks to see if remote was added to project

2.) Open directory in VSCode/text editor:

`code .` or `code-insiders .`

3.) Push any starter code to their remote master branch via their VSCode/text editor terminal - _make sure to save file(s) before adding_:

`git add -A`  
`git commit -m "first push to remote repo"`  
`git push origin master`

---

<br>

### **Developer** steps:

1.) Head to **GitHub manager's** remote master branch on GitHub

2.) Press `Fork` button --> will bring you to your forked version of their master repository

3.) Press green `Code` button, and copy URL path for cloning

4.) Head to where you store your projects on your computer

5.) Run this command:

`git clone <name-of-copied-fork-url>`  
--> this should create directory for your project

6.) cd into this directory, then open it in VSCode:

`cd <project-name>`  
`code .` or `code-insiders .`

7.) Add an **upstream remote** to your directory:

\* _master remote_ --> url for forked version of GitHub manager's remote repository (should be present already)  
\* _upstream remote_ --> url for GitHub manager's remote repository

`git remote add upstream <url-of-GitHub-manager-remote-repo>`  
`git remote -v` \* should yield two repositories, both origin and upstream

8.) Create separate dev branch

`git checkout -b dev`

\* This branch will be for your development of the code and for any pull requests to the GitHub manager's master remote.  
\* **Your master is the branch that will be only be used for pulling down from the GitHub manager's master remote, not development of code.**

9.) Add your code, _making sure you won't be conflicting with anyone else's contributions or deleting any important code._

10.) Save your file(s), and then add, commit, and push to your **dev** branch:

`git push origin development`

\* **Always push to your remote dev branch before making any pull requests.**

11.) Head to your forked repository on GitHub, and administer a **pull request**:

- Make sure you make pull request to the **GitHub manager's master** from your **dev branch**
- After you push to your dev branch, you may see a green box pop up on your remote repo page, letting you know you can administer a pull request to the GitHub manager's master. You can do this from here, OR
- Underneath the nav options `Go to file`, `Add to file`, and the green button `Code`, there should be an option for clicking `Pull request`. You can do this here as well.

<br>

12.) Once pull request is approved (you will be notified if approved, denied or merge conflict happens. GitHub manager will resolve any conflicts and reach out for further steps)

13.) After approval, head back to your VSCode/local branches. Check out to your master branch:

`git checkout master`

14.) Run command for pulling down code from upstream:

`git pull upstream master`

15.) Save your file. Add, commit and push to your master branch.

16.) Checkout to your development branch:

`git checkout development`

17.) Merge your pulled-down changes to your dev branch:

`git merge master`

18.) Start process over again **Step 11** until project is complete
