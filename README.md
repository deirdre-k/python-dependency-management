# Workshop on Python Dependency Management

An intro to Python packages and how to manage them

## Prerequisites

To complete, you'll need the following installed on your computer

* Code editor of choice, we recommend VSCode or PyCharm
* [Python](https://www.python.org/downloads/)
* GitHub account
* Git set up and logged in locally (see [tutorial](https://docs.github.com/en/get-started/git-basics/set-up-git))
* Optional: [conda](https://www.anaconda.com/docs/getting-started/miniconda/install#quickstart-install-instructions)

## Set up

1. Fork this repository:
  Create your own copy of this repository by clicking the "Fork" button in the top right corner of this page. This will create a copy of the repository under your GitHub account that you can modify.

2. Clone the repository:
  Clone your forked repository to your local computer:
1. Open your terminal:
     * Windows: Press Windows key, type "cmd", press Enter
     * Mac: Press Cmd + Space, type "terminal", press Enter

2. Navigate to your preferred folder:

     ```bash
     cd Documents   # Windows
     cd ~/Documents # Mac
     ```

     Use `dir` (Windows) or `ls` (Mac) to see available folders
     Use `cd FOLDER_NAME` to navigate into a folder
     Use `mkdir FOLDER_NAME` to create a new folder

3. Clone the repository (replace `YOUR-USERNAME`):

     ```bash
     git clone https://github.com/YOUR-USERNAME/python-dependency-workshop.git
     cd python-dependency-workshop
     ```

  If you get errors, verify that:

* You replaced YOUR-USERNAME with your GitHub username
* Git is installed and you're logged in
* You're in the correct folder

## Contents

This repo has a series of exercises in the `workshop_exercises` directory that walk through different ways of creating virtual environments and managing dependencies in Python. They are intended to be completed in order, but you can jump in at the level you feel comfortable.

### Exercises

* Exercise 1: Setting Up a Virtual Environment
* Exercise 2: Managing Dependencies with requirements.txt
* Exercise 3: Pyproject.toml, Editable Mode, and Optional Dependencies
* Exercise 4: Setting Up a Conda Environment with environment.yml
* Exercise 5: Using pyproject.toml with Poetry
* Exercise 6: Using requirements.in

### Practice Problems

If you feel confident in the exercises, you can move on to the `practice_problems` directory, which has a series of projects with issues in their dependency management. Try your best to debug them. For each, you can find the answer to what's broken in the `answer.txt` file.
