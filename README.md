In the fast-paced world of DevOps, seamless collaboration and efficient version control are critical to managing codebases, automating workflows, and deploying applications across multiple environments. Git, a distributed version control system, has become the backbone of modern DevOps practices, enabling teams to collaborate effortlessly, track changes, and manage infrastructure as code.

Whether you’re an absolute beginner or looking to sharpen your Git skills for advanced use cases in a DevOps environment, this guide will provide you with a comprehensive roadmap. We’ll start with the basics of setting up and using Git, and gradually dive into advanced workflows that are essential for working in large-scale, production-level environments. By the end, you’ll not only be comfortable with Git commands but also equipped with the expertise needed to integrate Git into CI/CD pipelines, automate infrastructure, and enable a GitOps workflow.

If you’re aiming for a career at top tech companies like Amazon, Google, or Netflix, this tutorial will give you the foundational Git skills you need to thrive in a DevOps role.


Introduction to Git
Git is a distributed version control system that tracks changes in your code during software development. It allows multiple people to collaborate on the same project simultaneously, keeping track of changes made to the project over time.

Key Concepts:
Repository (Repo): A directory that contains your project’s files and a history of changes. Every project tracked by Git has a repository.
Branch: A version of your project’s repository. Branches are used to work on separate features or fixes without affecting the main code.
Commit: A saved snapshot of changes made to files in a repository. Think of it as a checkpoint in your project’s history.
Merge: The process of integrating changes from one branch into another (usually into the main branch).
1. Installing Git
Git is available for all major operating systems. Install it by following the instructions for your platform:

Windows: Download Git from git-scm.com and install it.
Mac: Use Homebrew to install Git.
brew install git
Linux: Install Git using your package manager.
sudo apt-get install git  # For Debian-based systems
sudo yum install git  # For RedHat-based systems
Verify the installation:

git --version
2. Setting Up Git
After installation, configure your Git identity, which is used to identify who is making changes to the code

git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
Verify your configuration:

git config --list
3. Initializing a Repository
To start tracking a project with Git, navigate to your project folder and initialize a repository. This turns your folder into a Git repository, creating a .git folder where Git will store project history:

cd your-project
git init
The git init creates a .git folder, where Git stores the project history (This is a hidden folder)

4. Basic Git Workflow
Let’s understand the basic git workflow by following a series of hand-on activities.

4.1. Adding Files to the Staging Area
After you’ve made changes to your files, you must first “stage” them. The staging area is like a holding area where Git keeps track of changes before they are committed. Staging allows you to review changes before saving them in the repository.

git add filename.txt
To add all files:

git add .
4.2. Committing Changes
Once files are staged, you can “commit” them. A commit is like a checkpoint in your project’s history, capturing the current state of your files. Every commit should have a message explaining what changes were made.

git commit -m "Initial commit"
4.3. Viewing Commit History
To see a list of previous commits (and who made them):

git log
5. Working with Branches
Branches allow you to work on new features, bug fixes, or experiments without affecting the main codebase.

5.1. Creating and Switching Branches
Create a new branch:

git branch feature-branch
Switch to the branch:

git checkout feature-branch
Alternatively, create and switch in one step:

git checkout -b feature-branch
5.2. Merging Branches
After you finish working on your branch, you can merge it into the main branch to include your changes in the project.

Switch back to the main branch (usually called main or master):
git checkout main
2. Merge the feature branch into main:

git merge feature-branch
3. Delete the feature branch (optional)

git branch -d feature-branch
6. Collaborating with Remote Repositories
Remote repositories allow you to collaborate with others by pushing and pulling changes to and from a central repository hosted on services like GitHub or GitLab.

6.1. Cloning a Remote Repository
If you want to start working on an existing project, clone it from the remote repository:

git clone https://github.com/username/repository.git
6.2. Adding a Remote
If you have a local repository, you can link it to a remote server:

git remote add origin https://github.com/username/repository.git
6.3. Pushing Changes
To share your changes, push them to the remote repository:

git push origin branch-name
6.4. Pulling Changes
To get the latest changes from the remote repository:

git pull origin branch-name
7. Advanced Git Features for DevOps
7.1. Git Rebase
Rebasing integrates changes from one branch into another but rewrites commit history to make it linear. This is useful for cleaning up a messy commit history.

git checkout feature-branch
git rebase main
7.2. Git Stash
If you’re not ready to commit your work but need to switch branches, you can “stash” your changes:

git stash
To reapply the stashed changes later:

git stash apply
7.3. Git Tagging
Tags mark specific commits, often used to denote release versions:

git tag v1.0
Push tags to the remote repository:

git push origin --tags
7.4. Git Hooks
Git hooks are scripts that automatically run when certain events occur in your repo (like committing or pushing).

Example: To create a pre-commit hook:

Go to .git/hooks/.
Rename pre-commit.sample to pre-commit.
Add your script inside the file.
7.5. Git Submodules
Submodules allow you to keep a Git repository inside another Git repository. This is useful for managing dependencies:

git submodule add https://github.com/username/submodule-repo.git
8. Git in Continuous Integration/Continuous Deployment (CI/CD)
In DevOps, Git is essential for automating testing, building, and deploying software.

8.1. Git in CI/CD Pipelines
You can integrate Git with CI/CD tools like Jenkins, CircleCI, and GitHub Actions to automate workflows.

Trigger Builds: Automatically run tests when new code is pushed.
Deploy Code: Push code to staging or production environments.
8.2. Example: GitHub Actions
What are GitHub Actions?
GitHub Actions is a powerful automation tool integrated directly into GitHub, enabling you to automate tasks within your software development lifecycle. Whether it’s building, testing, deploying code, or managing issues, GitHub Actions allows you to create custom workflows that respond to various events in your repository.

Key Features of GitHub Actions
Workflow Automation:
Automate repetitive tasks such as code compilation, testing, and deployment.
Trigger workflows based on specific events like pushes, pull requests, or on a scheduled basis.
2. Continuous Integration and Continuous Deployment (CI/CD):

Streamline the process of integrating code changes and deploying applications.
Ensure that code is automatically tested and deployed whenever changes are made.
3. Customizable and Extensible:

Utilize pre-built actions from the GitHub Marketplace or create your own.
Combine multiple actions to build complex workflows tailored to your project’s needs.
Cross-Platform Support:

Run workflows on different operating systems, including Linux, macOS, and Windows.
Secrets Management:

Securely store and manage sensitive information like API keys and tokens used in workflows.
Core Components of GitHub Actions
Workflows:
Defined using YAML files, workflows specify the automated processes you want to execute.
Stored in the .github/workflows/ directory of your repository.
2. Events:

Triggers that initiate workflows. Examples include push, pull_request, release, or even scheduled times.
3. Jobs:

A workflow is composed of one or more jobs. Each job runs in a fresh instance of a virtual environment.
Jobs can run sequentially or in parallel.
4. Steps:

Individual tasks within a job. Each step can execute commands or run an action.
5. Actions:

Reusable units of code that perform specific tasks. Actions can be built-in, from the GitHub Marketplace, or custom-defined.
6. Runners:

Servers that execute the jobs. GitHub provides hosted runners, or you can host your own.
Creating a GitHub Actions Workflow: Step-by-Step
Let’s walk through creating a simple GitHub Actions workflow that automatically runs tests whenever code is pushed to the main branch.

Please refer the respective documentation as there could be minor changes in steps (I am just putting here the below steps for quick reference)

Step 1: Navigate to Your Repository
Go to your GitHub repository where you want to set up the workflow.
Step 2: Access the Actions Tab
Click on the “Actions” tab at the top of the repository page.
GitHub may suggest some starter workflows. For this example, we’ll create a custom workflow.
Step 3: Create a New Workflow File
Click on “New workflow”.
Choose “Set up a workflow yourself” to create a custom YAML file.
Name your workflow file, for example, ci.yml.
Step 4: Define the Workflow
Here’s an example of a basic GitHub Actions workflow:

name: CI

# Trigger the workflow on push events to the main branch
on:
  push:
    branches: [ main ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
      # Step 1: Checkout the repository code
      - name: Checkout code
        uses: actions/checkout@v2

      # Step 2: Set up Node.js environment
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '14'

      # Step 3: Install dependencies
      - name: Install dependencies
        run: npm install

      # Step 4: Run tests
      - name: Run tests
        run: npm test
Step 5: Commit the Workflow File
After defining your workflow, commit the new YAML file to the .github/workflows/ directory.
GitHub will automatically recognize and activate the workflow.
Step 6: Observe Workflow Execution
Trigger the workflow by pushing changes to the main branch.
Navigate to the “Actions” tab to monitor the workflow’s progress and view logs.
Understanding the Workflow Example
name: Assigns a name to the workflow (CI in this case).
on:
- push: Specifies that the workflow should run on push events to the main branch.
jobs:
build-and-test:
- Defines a job named build-and-test.
- runs-on: Specifies the runner environment (ubuntu-latest).
steps:
- Checkout code:
- Uses the actions/checkout@v2 action to clone the repository code into the runner.
Setup Node.js:
- Utilizes the actions/setup-node@v3 action to set up a Node.js environment with version 14.
Install dependencies:
- Runs npm install to install project dependencies.
Run tests:
Executes npm test to run the test suite.
Advanced GitHub Actions Features
Matrix Builds:Run jobs with different configurations simultaneously. For example, testing across multiple Node.js versions.
jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [12, 14, 16]
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm install
      - run: npm test
2. Caching Dependencies:

Speed up workflows by caching dependencies.
- name: Cache Node.js modules
  uses: actions/cache@v3
  with:
    path: ~/.npm
    key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
    restore-keys: |
      ${{ runner.os }}-node-
3. Secrets and Environment Variables:

Securely use sensitive data within workflows.
- name: Deploy to AWS
  env:
    AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
    AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
  run: aws deploy ...
4. Reusable Workflows:

Define workflows that can be reused across multiple repositories.
jobs:
  call-workflow:
    uses: owner/repo/.github/workflows/reusable-workflow.yml@v1
    with:
      some-input: value
9. Git Best Practices for DevOps
Commit Often: Make small, frequent commits.
Write Clear Commit Messages: Be descriptive in your messages (e.g., git commit -m "Fix login issue").
Use Branches for Features: Always create a new branch for each feature.
Review Pull Requests: Ensure team members review and approve code before merging.
Automate with CI/CD: Integrate Git with automation tools to ensure consistency and reduce manual intervention.
Conclusion
Git is a powerful tool for DevOps, allowing for efficient collaboration, code management, and integration into CI/CD pipelines. By following this tutorial, you can master Git from basic commands to advanced workflows for DevOps.

PS: This tutorial is a WIP and more diagrams and descriptions will be added.
