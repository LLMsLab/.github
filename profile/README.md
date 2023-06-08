# Introduction to the LLMsLab Project

Welcome to the LLMsLab project, an experimental playground designed
specifically for the exploration of large language models. Our mission
in this project is to facilitate rapid prototyping and deployment of
applications built atop these models, utilizing the power and
flexibility of Hugging Face Spaces. 

Through a robust Continuous Integration and Continuous Deployment
(CI/CD) approach, we aim to streamline the process of bringing these
applications to life. We hope that this initiative will foster a deeper
understanding of large language models and encourage innovative uses for
them.

Whether you are a researcher, a developer, or an enthusiast in the field
of AI, we invite you to join us in this exciting journey.

This document contains the following guides:

- [LLMsLab Infrastructure](https://github.com/LLMsLab#llmslab-infrastructure)
- [MLOps with Hugging Face Spaces, Gradio and GitHub Actions](https://github.com/LLMsLab#mlops-with-hugging-face-spaces-gradio-and-github-actions)
- [How to Contribute](https://github.com/LLMsLab#how-to-contribute)

# LLMsLab Infrastructure

<a href="https://huggingface.co/LLMsLab">
  <img src="https://huggingface.co/datasets/huggingface/brand-assets/resolve/main/hf-logo.png" width="60" alt="Join our Hugging Face organization">
</a>
<a href="https://llmslab.slack.com">
  <img src="https://img.icons8.com/color/48/slack-new.png" width="60" alt="Join our Slack workspace">
</a>
<a href="https://colab.research.google.com/">
  <img src="https://img.icons8.com/color/48/google-colab.png" width="60" alt="Google Colab">
</a>


- **Version Control:** We leverage **GitHub**, a robust platform for
collaborative coding and version control.
- **IDEs:** Our toolkit includes **Visual Studio Code** for a powerful
local development environment, **GitHub Codespaces** for seamless online
development, and **Google Colab** for convenient, web-based Jupyter
notebooks.
- **Build & Automation:** **GitHub Actions** serves as our core CI/CD
tool, automating testing, building, and deployment tasks.
- **AI Model Interfaces:** We use **Gradio** and **Hugging Face Spaces**
to create interactive, user-friendly interfaces for our AI models.
- **Database Systems:** When necessary, we incorporate **Vector
Databases** to manage our data effectively.
- **Project Management:** **Jira Software** helps us track tasks, bugs,
and progress, ensuring our projects are well-organized and on track.
- **Communication:** We use **Slack** for instant communication, fostering
a dynamic and collaborative work environment.
- **Project Management Philosophy:** We adopt an **Agile** approach with
- **Kanban**, promoting continuous delivery and flexible response to
change.

##  LLMsLab Repositories


- **chat-gpt-api-lab**: A sandbox for testing, playing, and
  experimenting with the various components and capabilities of the
  ChatGPT API
- **qa-app-lab**: A sandbox for developing question answering
  applications using real insurance chat data
- **model-lab**: An experimentation playground for exploring and
  harnessing the power of open-source large language models
- **langchain-lab Public**: A sandbox for testing, playing, and
  experimenting with the various components and capabilities of the
  LangChain framework

# MLOps with Hugging Face Spaces, Gradio and GitHub Actions

<img
src="https://huggingface.co/datasets/huggingface/brand-assets/resolve/main/hf-logo.png"
width=90 alt="abc"/> <img
  src="https://res.cloudinary.com/crunchbase-production/image/upload/c_lpad,f_auto,q_auto:eco,dpr_1/tv8zrejyehjshagvxgt7"
  width=200/> <img
  src="https://voltrondata.com/assets/images/resources/2023-02-16/main-image-blog.jpg"
  width=200/>

> This article details an end-to-end process for creating an app on top of Large 
Language Models, showcasing an example of MLOps with Hugging Face Spaces, Gradio, 
and GitHub Actions. We will follow the steps of setting up a repository similar 
to the one shared on GitHub, which can be found 
here: [hugging-face-demo](https://github.com/markeyser/hugging-face-demo). 
The resulting product of this procedure is a text summarization application 
that is hosted and operational on Hugging Face Spaces, 
viewable at this link: [Demo](https://huggingface.co/spaces/magkey/demo). 

> The entire process is carefully outlined in an accompanying YouTube 
guide, which offers step-by-step visuals to help ensure a seamless setup. 
You can access the guide here: [MLOps Tutorial Video](https://youtu.be/VYSGjUa5sc4). 
By utilizing this tutorial, you'll learn to deploy robust applications on 
Hugging Face Spaces, enabling you to leverage the power of Large 
Language Models in your own projects. 

This tutorial illustrates how to deploy an application on Hugging Face
Spaces using continuous delivery, a true ML Ops workflow.

Let's take a look at this application of a Hugging Face MLOps workflow:

```mermaid
graph TD
    A([Hugging Face]) --> B[/Authentication/]
    B --> C{{Token}}
    C --> D{GitHub Codespace & GitHub Actions}
    D --> E([Hugging Face Spaces])
    E --> F[[Gradio App]]
    F --> G(Text Summarization)
    D --> J([Hugging Face/Open AI Models])
```

- The first step involves accessing Hugging Face, which necessitates an
  authenticated account. 
- Upon successful authentication, a token is generated which serves as a
  key for the subsequent steps.
- The token is then used to launch a GitHub Codespace, a cloud-based
  development environment that enables us to develop the application
  locally.
- Following the development phase, the application is programmatically
  pushed using GitHub Actions. This step is crucial as it automates the
  workflow and facilitates continuous integration and deployment.
- During this process, a Hugging Face/Open AI model is pulled into the
  workflow. This model is a key component of our application, providing
  the machine learning capabilities we need.
- The application is then moved into Hugging Face Spaces, an environment
  designed for hosting and sharing machine learning models and
  applications.
- With the help of a technology called Gradio, an interactive
  application is built within the Hugging Face Spaces. Gradio is a
  powerful tool for creating user-friendly interfaces for machine
  learning models.
- The final step involves the actual application use case - text
  summarization. This is where the real-world application of our
  workflow comes to fruition. Using the interactive Gradio app, users
  are able to perform text summarization tasks leveraging the
  capabilities of the underlying Hugging Face model.

## Getting Started with Hugging Face: Account Setup, Models Exploration, and Continuous Delivery Overview

- We begin our journey by accessing [Hugging
  Face](https://huggingface.co/), an essential platform for machine
  learning models and applications.
- The initial step necessitates the creation of an account on Hugging
  Face. Without an account, one cannot leverage the platform's
  resources.
- Once the account is set up, we can explore the diverse sections of the
  platform, such as Models, Datasets, Spaces, Docs, Solutions, and
  Pricing. However, our primary focus in this context is on the
  [Models](https://huggingface.co/models) and
  [Spaces](https://huggingface.co/spaces) sections.
- An overview of Hugging Face reveals that the 'Models' section is
  particularly powerful. It offers a wide range of functionalities and
  hosts a staggering number of models.
- The 'Spaces' section is designated for hosting machine learning
  applications. It's a dedicated space where developers can deploy their
  applications and make them accessible to users.
- The platform also supports continuous delivery, meaning that updates
  and improvements can be frequently and automatically deployed. This
  ensures that the latest and best version of your application is always
  available to users. 


## Creating and Setting Up a New Hugging Face Space with Gradio

- The first step involves the creation of a new space on Hugging Face,
  which we will refer to as 'Demo'.
- Within this newly created space, an appropriate license, such as
  Creative Commons, is assigned.
- Subsequently, Gradio is selected as the preferred solution for serving
  the MLOps application. Gradio is an excellent tool for creating
  user-friendly interfaces for machine learning models.
- Following the selection of Gradio, the creation of the space is
  confirmed by clicking on 'Create Space'.
- The process thus far is quite straightforward. 

## Cloning the Repository and Setting Up GitHub Code Spaces for Development

- The next phase involves cloning the repository to start the
  development process in a different environment.
- In this scenario, GitHub Code Spaces is the preferred development
  environment. GitHub Code Spaces, a cloud-based platform, provides
  facilities for coding, building, testing, debugging, and deploying
  applications.
- The culmination of the process lies in pushing the code changes
  through GitHub Code Spaces. This step enables the deployment of
  updates, making them accessible within the Hugging Face space.
- To initiate this, we navigate to GitHub and opt to create a new
  repository. The repository is named 'hugging-face-demo' for easy
  identification.
- The repository is then furnished with a `README` file, which serves as
  a manual or guide for the repository. Additionally, a Python
  `.gitignore` file is included to specify files that Git should ignore.
- Lastly, a Creative Commons license is applied to the repository for
  copyright purposes. Following these steps, the repository is ready for
  use.

## Enabling and Launching a High-Performance Environment in GitHub Code Spaces

- The versatility of our current environment is highlighted by its
  ability to adapt and enable different development settings. 
- By clicking on the 'Code' button, a new environment, namely 'Create
  Code Spaces', can be activated. 
- 'Code Spaces' offers significant benefits, especially for machine
  learning tasks. It provides the option to choose a more expansive
  environment, one equipped with higher computational resources.
- To illustrate, one can select an environment with impressive
  specifications, such as a 16-core processor, 32 gigabytes of RAM, and
  128 gigabytes of storage. 
- After selecting the desired environment, the next step is to launch
  it. This action will initialize the environment, making it ready for
  use.

## Setting Up a Project Scaffold with a Virtual Environment and Necessary Files

- The subsequent step is the development of a project scaffold. A
  project scaffold, or structure, is a recommended starting point for
  any project. It provides a clear framework and facilitates a smooth
  start.
- An important part of setting up the project is creating a virtual
  environment. A virtual environment is beneficial as it allows for
  isolated spaces for Python projects, ensuring that each project can
  have its own dependencies, irrespective of what dependencies every
  other project has. Open the terminal an enter the following command `$
  virtualenv ~/.venv` to create the virtual environment.
- Once the virtual environment is created, the next task is to modify
  the `.bashrc` file. This file is a script that is run whenever a new
  terminal session is started. By adding a 'source' command at the end
  of the `.bashrc` file, the virtual environment is activated every time
  a new shell is opened. Follow these steps:
    - Open your terminal.
    - Type `nano ~/.bashrc` and press `Enter`. This will open your
      `.bashrc` file in the nano editor. If you're not in your home
      directory, you can also use the full path: `nano
      /home/yourusername/.bashrc`.
    - Using the arrow keys, navigate to the bottom of the file.
    - At the bottom, add the following line `source
      ~/.venv/bin/activate` This line of code will activate the virtual
      environment located at `~/.venv` each time a new terminal session
      starts.
    - Once you've made the changes, press `Ctrl+O` to write out (i.e.,
      save) the file. Confirm the file name `.bashrc` by simply pressing
      `Enter`.
    - Now, exit nano by pressing `Ctrl+X`.
    - For the new changes to take effect, you need to source the
      `.bashrc` file. You can do this by typing `source ~/.bashrc` in
      the terminal and pressing `Enter`. This will immediately apply the
      changes you've made without having to close and reopen your
      terminal

- With the virtual environment set up, a requirements file is created by
  using `$ touch requirements.txt`. This file is a way to specify and
  install necessary Python dependencies for the project.
- Next, an `app.py` file is created by using `$ touch app.py`. This is
  typically the main application file where the main logic of the
  project is written.
- Lastly, a makefile is created using `$ touch Makefile`. A makefile is
  a special kind of file that's used to manage and organize tasks within
  a project, like compiling and linking code. Paste in the Makefile the
  following:

```makefile
install:
	pip install --upgrade pip &&\
		pip install -r requirements.txt

test:
	python -m pytest -vvv --cov=hello --cov=greeting \
		--cov=smath --cov=web tests
	python -m pytest --nbval notebook.ipynb	#tests our jupyter notebook
	#python -m pytest -v tests/test_web.py #if you just want to test web

debug:
	python -m pytest -vv --pdb	#Debugger is invoked

one-test:
	python -m pytest -vv tests/test_greeting.py::test_my_name4

debugthree:
	#not working the way I expect
	python -m pytest -vv --pdb --maxfail=4  # drop to PDB for first three failures

format:
	black *.py

lint:
	pylint --disable=R,C *.py

all: install lint test format
```

- With these steps, the project scaffold is completed and the
  development process can be commenced with ease.

## Populating the Makefile and Managing Project Dependencies

- Given that some of the necessary components have already been
  prepared, these elements will be copied into the current project. 
- The focus at this juncture is the makefile. Content will be pasted
  into the makefile from a previously constructed one.
- It's important to note that the primary advantage of using a makefile
  is its capacity to manage dependencies effectively. A makefile can
  automate the process of installing and updating project dependencies,
  ensuring that all necessary libraries and modules are available when
  needed.

```makefile
install:
	pip install --upgrade pip &&\
		pip install -r requirements.txt
```

## Specifying Project Dependencies in the Requirements File

- Additionally, a requirements file will be populated with the necessary
  dependencies for the project. This file is crucial for defining the
  exact libraries and modules the project needs to function properly.
- Key dependencies to be included in the requirements file are Gradio
  and Transformers. These libraries provide functionalities that are
  integral to the project.
- Personal preference also factors into the selection of libraries. In
  this instance, TensorFlow is chosen as the preferred machine learning
  framework and will therefore be included in the requirements file.

This is the content to include in the `requirements.txt` file:

```txt
gradio
transformers
tensorflow
```

## Developing the Application Code and Launching the Application with Code Spaces

- The next phase of the process involves writing the application code,
  `app.py`. The application will leverage the Transformers library,
  which facilitates the loading of any model from TensorFlow.
- Gradio, a library used for creating user-friendly interfaces for
  machine learning models, will also be incorporated. The interface will
  be constructed within the application.
- The application will contain a model and a 'predict' function. The
  function's role is to fetch the output from the model and perform text
  summarization.
- Using the 'gr.blocks' module from Gradio, a text block will be created
  for the interface.
- With just a few lines of code, a fully functional application capable
  of summarizing text can be realized.
- To initiate the application, a `$ make install` command is executed.
  This command will install the necessary dependencies as specified in
  the makefile.
- Executing `$ make install` allows the application to take advantage of
  the robust environment provided by Code Spaces. This preference for
  Code Spaces and cloud development, in general, stems from the ability
  to utilize powerful machines on a temporary basis, as needed.


```python
from transformers import pipeline
import gradio as gr


model = pipeline(
    "summarization",
)


def predict(prompt):
    summary = model(prompt)[0]["summary_text"]
    return summary


# create an interface for the model
with gr.Interface(predict, "textbox", "text") as interface:
    interface.launch()
```

Check the application by pasting some text to summarize.

First run the application:

```bash
$ python app.py
```

Pass some text to summarize.


## Preparing for Deployment: Generating Hugging Face Access Token and Configuring GitHub Secrets

- While the interactive nature of the application is beneficial for
  testing and development, the ultimate goal of MLOps is to move the
  application into production. This requires several additional steps.
- The first step involves navigating to the Hugging Face platform and
  accessing the user profile settings. From the settings menu, access
  tokens can be created.
- A new access token with read and write permissions is generated.
  Choose both, the read and write roles. This token is designated for
  GitHub Actions deployment. The name of the new access token could be
  `github-actions-deploy`.
- Once the token is created, it can be copied for later use.
- Returning to the GitHub repository, the next step is to navigate to
  the repository settings on GitHub. Here, the 'Secrets' section is
  accessed.
- Within 'Secrets', a new secret for GitHub Actions can be created. This
  secret will hold the copied Hugging Face token.
- The new secret is named (for example, "HG") and the copied token is
  pasted into the corresponding field. After adding the secret, the
  token is securely stored and ready to facilitate deployment.


## Preparing for Deployment: Updating the README File for Correct Application Configuration

- If you navigate back to Hugging Face and access your spaces, go to the
  "demo" application and then "Files and versions" and copy the content
  of the 'README.md' file. 
- The 'README' file in the repository is of particular importance. This
  file contains a specific structure that must be adhered to in order to
  correctly configure your application.

Update your `README.md` to include the following at the very top of the
file:

```Markdown
---
title: Demo
emoji: 🌖
colorFrom: purple
colorTo: purple
sdk: gradio
sdk_version: 3.0.6
app_file: app.py
pinned: false
license: cc
---


[![Sync to Hugging Face hub](https://github.com/markeyser/hugging-face-demo/actions/workflows/main.yml/badge.svg)](https://github.com/markeyser/hugging-face-demo/actions/workflows/main.yml)

# hugging-face-demo
Devoted to understand how to use Hugging Face Spaces, Gradio and GitHub Action for DevOps (CD)

[Try Demo Text Summarization Here](https://huggingface.co/spaces/magkey/demo)


## References

[Watch YouTube Walkthrough](https://youtu.be/VYSGjUa5sc4)
```

- With this step complete, the only task remaining to enable deployment
  is to edit the corresponding GitHub Action.

## Preparing for Deployment: Creating GitHub Action for Deployment and Synchronizing with the Remote Repository

- The next phase involves creating a GitHub Action. To create an accion
  use the "Actions" button and choose "Skip this and set up a workflow
  yourself". Now add your `main.yml` file and paste the following
  content in:

```yml
# This is a basic workflow to help you get started with Actions

name: Sync to Hugging Face hub


# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but
  # only for the main branch
  push:
    branches: [main]
  pull_request:
    branches: [main]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run
# sequentially or in parallel
jobs:
  # This workflow contains a single job called "sync-to-hub"
  sync-to-hub:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest
    
    # Steps represent a sequence of tasks that will be
    # executed as part of the job
    steps:
      # Check-out your repository under $GITHUB_WORKSPACE,
      # so your job can access it
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0
          
      # Runs a single command using the runners shell
      - name: Add remote 
        env:
          HF: ${{ secrets.HF }}
        run: git remote add space https://magkey:$HF@huggingface.co/spaces/magkey/demo
      
      # Runs a set of commands using the runners shell
      - name: Push to hub
        env:
          HF: ${{ secrets.HF }}
        run: git push --force https://magkey:$HF@huggingface.co/spaces/magkey/demo main
```

Where:

```
https://HF_USERNAME:$HF_TOKEN@huggingface.co/spaces/HF_USERNAME/SPACE_NAME
```

- `HF_USERNAME` = `magkey` - user's username on Hugging Face
- `$HF_TOKEN` = `$HF` - Hugging Face Access Token
- `SPACE_NAME` = `demo` - Hugging Face Spaces appliacation's name


Ref: https://huggingface.co/docs/hub/spaces-github-actions

- Upon inspection, it's evident that the action code is correctly
  configured. It will leverage the secret generated earlier and execute
  a 'git remote add' command, targeting the Hugging Face space.
- The push target in this instance corresponds to a specific code space,
  'demo' for example. It's essential that this target matches the name
  of the code space within Hugging Face.
- After the action is correctly set up, it's committed to the repository
  by run `Commit chages`. Once it is commited is ready to go and it'll
  start synchronizing remotelyOnce committed, the action is ready for
  execution.
- The action synchronizes with the remote repository and commences
  operation. These are the crucial steps required to deploy the
  application.

## Continuous Deployment and Verification of the Application

- After setting up the environment correctly, every subsequent
  modification will trigger an automatic deployment to production. This
  is the essence of the continuous delivery approach implemented in this
  project.
- To keep track of ongoing deployments, a GitHub Actions badge can be
  added to the repository. This badge provides real-time status updates
  about the deployment processes.
- To validate the functionality of the application, one can return to
  the Hugging Face platform and select their profile. Within the
  profile, there are two spaces: the original space and the continuous
  delivery space.
- By selecting the continuous delivery space, it is possible to interact
  with the deployed application. For instance, blocks of text can be
  entered for processing by the application.
- The application runs within the Hugging Face interface, signifying
  successful deployment. This fully deployed application can be shared
  with other users who can also interact with it in real time.
- Upon completion of a task, the application displays the output,
  confirming its successful operation.

# How to Contribute

Thank you for investing your time in contributing to our project!

Welcome to our contribution guide. As we strive to maintain a high
standard of quality and consistency in our work, we have adopted a set
of prescriptive steps and best practices encapsulated within the [Data
Science Lifecycle Process (DSL-P)](https://github.com/dslp/dslp). 

The DSL-P provides a robust framework that enables data science teams to
consistently deliver value. It outlines a branching strategy that fits
the data science development flow, offers issue templates for various
types of data science work, and provides comprehensive guidance on how
to integrate all the necessary tools and workflows to make data science
work efficient and effective.

In this guide, we will closely follow the DSL-P documentation. We
believe this will enhance our collaboration, improve our productivity,
and ultimately lead to the delivery of high-quality data-driven
solutions. Whether you're a seasoned contributor or a newcomer to our
project, we encourage you to familiarize yourself with the DSL-P and
this guide to understand our workflow and expectations. 

We look forward to your valuable contributions!

## Introduction: GitHub Life-Cycle with Google CoLab Notebooks

The GitHub life-cycle is an effective way of managing and organizing
your code and collaboration with your team when working on projects,
particularly when Google CoLab notebooks are involved. This life-cycle
involves several steps that help streamline the development process and
ensure code quality and consistency. Here is a brief explanation of each
step:

1. **Open an Issue**: The life-cycle begins by opening an issue. An
   issue is a description of a task, feature, or bug that needs to be
   addressed in the project. It's a way of tracking individual work
   items and provides a place for discussing the work and any problems
   encountered.

2. **Create a Branch**: Once an issue has been opened, the next step is
   to create a branch where you'll do your work. Branches allow you to
   work on different tasks in isolation, without affecting the main (or
   other) branch of the project. This is particularly useful when
   working on complex projects where many people may be contributing to
   the codebase.

3. **Write Your Code with Google CoLab**: Now, you're ready to start
   coding! If you're using Google CoLab notebooks, you can link your
   notebook to your GitHub repository and save your work directly there.
   This is particularly useful for data science projects where you want
   to keep track of exploratory data analysis, model training details,
   and other steps of your work.

4. **Push Your Code**: After writing your code and testing it
   thoroughly, the next step is to commit your changes and push your
   code to GitHub. This updates your branch on GitHub with your latest
   changes.

5. **Create a Pull Request (PR)**: Once you've pushed your changes, the
   next step is to create a pull request. A pull request is a way of
   proposing your changes to the rest of the team. It allows others to
   review your code and give feedback before the changes are merged into
   the main branch. When creating a pull request, it's important to
   provide a clear and concise description of the changes you've made
   and the reason behind them.

6. **Review and Merge**: After a pull request has been created, it will
   be reviewed by another member of the team. They will look at your
   code, provide feedback, and eventually approve the changes. Once your
   pull request has been approved, it can be merged into the main
   branch. Merging finalizes the changes, adding them to the main
   codebase.

7. **Close the Issue**: Finally, once the changes have been merged and
   the task described in the issue has been completed, the issue can be
   closed. This signifies that the work has been completed.

This life-cycle provides a structured way to manage your code and
collaborate effectively with your team. By following these steps, you
can ensure that your code is reviewed and tested before it becomes part
of the main project, and that everyone on the team has a chance to
provide input and understand the changes being made.

## 1. Opening an Issue on GitHub

Opening an issue on GitHub is the first step in the GitHub life-cycle.
This allows you to clearly define the task, bug, or feature that needs
to be addressed in your project. Here's how to do it:

Navigate to the main page of the repository on GitHub.  Click on the
"Issues" tab.  Click on the "New issue" button.  You'll now be presented
with a list of issue templates, if they have been set up for your
project.

| Template Name              | Description                                                                                                    |
|----------------------------|----------------------------------------------------------------------------------------------------------------|
| Ask Issue Template         | Used for asking questions or seeking help about a particular aspect of the project.                            |
| Bug Report Template        | Used for reporting a bug or an issue in the codebase.                                                          |
| Data Acquisition Template  | Used when the work involves sourcing or acquiring new data for the project.                                    |
| Data Creation Template     | Used when new data needs to be created, such as synthetic data or modified versions of existing data.          |
| Experiment Issues Template | Used for planning and tracking experiments, such as new modeling approaches or feature engineering techniques. |
| Feature Request            | Used to propose new features or enhancements to the project.                                                   |
| Model Issues Template      | Used for issues related to building, tuning, or evaluating models.                                             |

Issue templates provide a standard structure for reporting different
types of issues, like bugs, feature requests, data acquisition tasks,
data creation tasks, experimental issues, or model issues. They are
extremely useful for maintaining consistency and clarity in the project.
Each template prompts the issue creator to provide necessary details
about the task at hand, helping to avoid miscommunication or missing
information.

To choose a template, click on the "Get started" button next to the
template that best matches the type of issue you want to report.

When opening an issue:

1.  **Choose the appropriate template:** This depends on the work to be
    done. For instance, if you're reporting a bug, use the Bug Report
    Template.
    
2.  **Assign a team member:** The person responsible for the issue
    should be assigned to it. This is typically a data scientist.
    
3.  **Add labels:** Labels help categorize and filter issues. They can
    indicate the nature of the issue (bug, enhancement), the project
    phase (data acquisition, preprocessing, modeling), or the urgency
    (high priority).
    
4.  **Include in the project:** If your repository uses the Projects
    feature of GitHub for project management, you should associate the
    issue with the relevant project.
    
5.  **Create a meaningful title:** The title should summarize the issue
    in a clear and concise way.
    
6.  **Reference links to other issues:** You can link related issues to
    provide more context and link the work being done. This is done in
    the description of the issue using the format `#issue_number`. For
    example, `This task is part of a larger effort to improve our data
    quality, as outlined in issue #12.`

## 2. Create a Branch

Working with branches is an integral part of any GitHub project.
Branches allow you to isolate your work from the main code base,
providing a safe space to experiment, develop new features, or fix bugs
without impacting the main project until your changes are ready. This
isolation reduces the risk of introducing errors and ensures the main
codebase remains stable. It also enables concurrent development, with
multiple contributors working on different features or fixes
simultaneously, each on their own branch.

### Branching Strategy

Our project follows the branching strategy outlined in the [Data Science
Lifecycle Process (DSL-P)](https://github.com/dslp/dslp). This approach
provides a structured and efficient way to manage changes, ensure code
quality, and streamline the integration of updates back into the main
project.

The DSL-P branching strategy involves creating a new branch for each
issue or feature. The branch name should clearly indicate its purpose,
following the naming conventions mentioned in the previous section. Once
you've completed your work on this branch, it is then merged back into
the main branch through a Pull Request.

Please remember to regularly pull the latest changes from the main
branch into your working branch to reduce the likelihood of merge
conflicts. Always ensure your branch is up-to-date before submitting a
Pull Request.

In the following sections, we will guide you through the process of
creating and naming a new branch, developing your changes, and creating
a Pull Request.

### Steps to Create a New Branch

Creating a new branch in GitHub is a straightforward process, and we
recommend following the steps provided in the official GitHub
documentation. The guide titled ["Creating and deleting branches within
your
repository"](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository)
provides a detailed walkthrough of the process.

Remember, changes made on this branch won't affect the `main` branch
until you're ready to merge your changes via a Pull Request.

### Branch Naming Conventions

Adopting a consistent branch naming convention is crucial for
maintaining a tidy and coherent Git repository. It helps in quickly
identifying what work is being done in different branches. Here's a
guide to naming your branches effectively in our project.

#### Guidelines

1. All branch names should be in lowercase.
2. Words in a branch name should be separated by a hyphen `-`.
3. The branch name should start with a category, followed by a `/`.
4. The branch name should be descriptive about the work being done on
   the branch.

For example, if you're working on a new feature related to user
authentication, your branch name would be `feature/user-authentication`.

#### Categories

Here's a table of some common categories used in branch naming:

| Category      | Definition                                                                                                                                                                   |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `feature/`    | This prefix is used for branches where new features are being developed.                                                                                                     |
| `bugfix/`     | This prefix is used for branches where bug fixes are being worked on.                                                                                                        |
| `hotfix/`     | This prefix is typically used for branches where urgent fixes are being made directly to a production environment.                                                           |
| `release/`    | This prefix is used for branches that prepare for a new production release. This usually involves final minor changes and versioning.                                        |
| `docs/`       | This prefix is used for branches that involve only changes to documentation, not to the application code itself.                                                             |
| `experiment/` | This prefix is used for branches where new, experimental ideas are being tested that may or may not ever make it into the main project.                                      |
| `refactor/`   | This prefix is used for branches where code is being refactored or cleaned up, without altering its external behavior.                                                       |
| `test/`       | This prefix is used for branches where new tests are being added or existing tests are being updated.                                                                        |
| `chore/`      | This prefix is used for branches where routine tasks or chores are being completed, such as dependency updates or minor tweaks that don't significantly affect the codebase. |

Examples of branch names following these conventions could be:

- `feature/payment-integration`
- `bugfix/login-error`
- `docs/contribution-guide`
- `refactor/clean-up-code`

Using a `/` as part of a branch name in Git helps to organize branches
into logical groups. This is not a built-in feature of Git, but rather a
naming convention that has been widely adopted by the developer
community.

The `/` character can be used to create a pseudo-directory structure
within your branch names, which makes them easier to manage and
understand.

For example, you might prefix feature branch names with `feature/`, bug
fix branches with `bugfix/`, and documentation branches with `docs/`.
This makes it clear what the purpose of each branch is at a glance. It
also groups branches of the same type together when you list them, which
can make them easier to navigate.

Let's say you have the following branches in your repository:

- `feature/user-authentication`
- `feature/payment-integration`
- `bugfix/login-error`
- `docs/contribution-guide`

By following this naming convention, you can tell at a glance what type
of work is being done on each branch. And if you have a lot of branches,
it helps keep them organized and manageable.

Following a consistent branch naming convention will not only make the
repository easier to navigate, but it will also make collaboration among
team members smoother and more efficient.

## 3. Write Your Code with Google CoLab

The following are Google CoLab instructions to use on your notebook.

### Checking Environment and Setting Up Google Colab

The following code ensures that Google CoLab is running the correct
version of TensofrFLow

```python
try:
  from google.colab import drive
  drive.mount('/content/drive', force_remount=True)
  COLAB = True
  print("Note: using Google Colab")
  %tensorflow_version 2.x
except:
  print("Note: not using Google Colab")
  COLAB = False
```

Here's a step-by-step explanation:

1.  The script first attempts to import the `drive` module from the
    `google.colab` package. This package and its modules are only
    available within the Google Colab environment.
    
2.  If the import is successful, it means the code is running on Google
    Colab. The script then mounts your Google Drive at the directory
    `/content/drive`. If a drive is already mounted at this location,
    the `force_remount=True` argument will unmount it and then remount
    it. This is useful if you've made changes to files in your Google
    Drive after initially mounting the drive.
    
3.  The variable `COLAB` is then set to `True` to indicate that Google
    Colab is being used.
    
4.  The line `print("Note: using Google Colab")` prints a message to the
    console to inform the user that the code is being run on Google
    Colab.
    
5.  The line `%tensorflow_version 2.x` is a magic command in IPython,
    which Google Colab is based on. This command ensures that the 2.x
    version of TensorFlow is installed. If a different version is
    currently installed, it will be uninstalled and the correct version
    will be installed.
    
6.  If any of the above steps fail (due to an `ImportError` because
    `google.colab` doesn't exist or some other exception), then the code
    inside the `except` block will run. This sets `COLAB` to `False` and
    prints a message to the console to inform the user that the code is
    not being run on Google Colab.

#### How to Deal with Sensitive Information

How to deal with sensititve information such as passwords, API keys, or
personal information directly in your notebooks.

Create an `.env` file to keep your sensitive data:

```env
HUGGINGFACEHUB_API_TOKEN=abcabcabcabcabcabcabcabc
OPENAI_API_KEY=abcabcabcabcabcabcabcabc
PINECONE_API_KEY=abcabcabcabcabcabcabcabc
GITHUB_API_KEY=abcabcabcabcabcabcabcabc
GIT_USER_NAME=your_username
GIT_USER_EMAIL=youremail@yahoo.com
```

> The `.env` file **should not** be uploaded to your GitHub repository
> (public or private), especially if it contains sensitive information.
> It's good practice to add `.env` to your `.gitignore` file to ensure
> it's not accidentally committed to the repository.

To use this approach in Google Colab, you would upload the `.env` file
to Google Drive, and then read it from your Colab notebook. Here's how
you can do it:

#### Upload your `.env` file to Google Drive

A possible would be saving your `.env` file in your `Projects` folder on
Google Drive.

#### Installing the python-dotenv library

```pyhton
!pip install python-dotenv
```
This line uses the `pip` command to install the `python-dotenv` library.
The `!` at the beginning allows the command to be run directly from the
notebook.

#### Importing necessary modules

```python
import os
from dotenv import load_dotenv
```

`os` is a standard Python library for interfacing with the operating
system. In this script, it's used to get environment variables.

`load_dotenv` is a function from the `dotenv` module which loads
environment variables from a `.env` file into the system's environment
variables.

#### Loading environment variables

Load the environment variables from the `.env` file:

```python
load_dotenv('/content/drive/MyDrive/path_to_your_.env_file')
```

This line uses the `load_dotenv` function to load the environment
variables from a `.env` file located at the path
`/content/drive/MyDrive/Projects/.env`.

#### Retrieving API keys from the environment

```python
huggingface_api_key = os.getenv("HUGGINGFACEHUB_API_TOKEN")
openai_api_key = os.getenv("OPENAI_API_KEY")
pinecone_api_key = os.getenv("PINECONE_API_KEY")
```

These lines use the `os.getenv` function to retrieve the values of
several environment variables. These are API keys and other sensitive
information that will be used later in the script.

Replace `path_to_your_.env_file` with the path to your `.env` file in
Google Drive.

Remember to adjust the sharing settings of the `.env` file in Google
Drive to minimize the risk of unauthorized access. And always ensure
your code does not unintentionally expose sensitive data.

To adjust the sharing settings of the `.env` file in Google Drive, you
can follow these steps:

1. Go to Google Drive (drive.google.com) and navigate to your `.env`
   file.
2. Right-click on the `.env` file and select "Share."
3. A window will open showing the current sharing settings. By default,
   files are private to you. 

   To make sure the file is private, in the "Share with people and
   groups" section, there should be only your account listed. If there
   are other accounts or groups listed, you can click on them and then
   click on the "Remove" button (trash bin icon) to remove their access.

4. Click "Done" to save your changes.

Regarding preventing the unintentional exposure of sensitive data in
your code, you can follow these guidelines:

1. Never hardcode sensitive data (like API keys, passwords, etc.)
   directly in your notebooks or scripts.
2. Be careful with print statements or other logging that might
   inadvertently display sensitive data.
3. When using an environment variable to store sensitive data, access it
   using `os.getenv('VAR_NAME')` instead of `os.environ['VAR_NAME']`.
   The latter will raise an error if the variable is not found,
   potentially interrupting your code, while the former will return
   `None`, which can be handled more gracefully.
4. When sharing notebooks, always clear outputs first. Some outputs
   might contain sensitive data, especially error messages.
5. Use a .gitignore file to prevent certain files (like your .env file)
   from being committed to a Git repository. Always double-check what
   files are being committed when you run `git add` and `git commit`.
6. Regularly review your code and the packages you use for any potential
   security vulnerabilities. If you're working on a project with other
   people, consider conducting code reviews to catch potential issues.

Following these guidelines can help reduce the risk of exposing
sensitive data.

If you want to avoid using the `.env` file and `python-dotenv` package,
you can consider using the following methods:

1. **Use Google Drive along with Python's standard file I/O
   operations:** Instead of storing your sensitive information in an
   `.env` file and using `python-dotenv` to load it, you can store it in
   a plain text file or a JSON file, and then read this file in your
   code. Here's an example with a JSON file:

```python
import json

# Assuming you have a JSON file on your Google Drive with structure:
# {
#     "HUGGINGFACEHUB_API_TOKEN": "your_api_token"
# }

with open('/content/drive/MyDrive/path_to_your_file.json', 'r') as f:
    secrets = json.load(f)

huggingface_api_key = secrets["HUGGINGFACEHUB_API_TOKEN"]
```

Replace `path_to_your_file.json` with the path to your JSON file in
Google Drive.

2. **Use Google Cloud Secret Manager:** If you're working on a
   professional project, you might consider using a cloud-based secret
   manager. Google Cloud Secret Manager is a good option if you're
   already using Google Cloud. This is more complex to set up, but
   provides a secure way to handle sensitive data.

Remember, no matter which method you use, you must always be cautious to
not expose your sensitive data. Always clear outputs that might contain
sensitive data, and be careful with who you share your notebooks.

### Unmount Google Drive

```python
drive.flush_and_unmount()
print('All changes made in this colab session should now be visible in Drive.')
```

This part of the code is used to unmount Google Drive from the Google
Colab environment and ensure that all changes made during the session
are saved and visible in Google Drive.

Here is a more detailed explanation:

- `drive.flush_and_unmount()`: This method unmounts the Google Drive
  from the current Colab runtime. The `flush_and_unmount` method ensures
  that all changes made to files in the mounted Google Drive during the
  Colab session are "flushed" (i.e., written and saved) to Google Drive
  before unmounting it. This method is used to prevent data loss due to
  unsaved changes when the runtime is disconnected. 

- `print('All changes made in this colab session should now be visible
  in Drive.')`: This line simply prints a message to the console to
  inform the user that all changes made during the Colab session should
  now be saved and visible in Google Drive.


## 4. Push Your Code

After writing and thoroughly testing your code, the next step is to
commit your changes and push your code to GitHub. This updates your
branch on GitHub with your latest changes. If you're working in Google
Colab, you can directly commit your changes to GitHub. 

### Pushing Changes from Google Colab to GitHub

1. Click on `File` in the upper menu of your Google Colab notebook.

2. Select `Save a copy in GitHub` from the dropdown list.

3. Choose the repository where you want to commit your changes.

4. Select the branch where you want to commit your changes. Remember to
   use the branch you created for the issue you are working on.

5. Write a clear and concise commit message in the space provided. This
   message should explain what changes you made and why.

6. Click on `OK` to finalize the commit and push your changes to the
   selected branch in your GitHub repository.

### Writing Good Git Commit Messages

When you commit your changes, you'll need to include a commit message.
This message is a brief summary of the changes you've made. Here are
some best practices to follow while writing your commit message:

1. **Keep it concise:** Ideally, your commit message should not exceed
   50 characters. It's not the place for detailed explanations; if more
   context is necessary, consider adding comments within your code.

2. **Use the imperative mood:** Write your commit message as if you are
   giving a command. For example, use "Add function to compute averages"
   instead of "Added function" or "Adds function."

3. **First line should be a summary:** The first line of the commit
   message should be a brief summary of the changes. If more detail is
   necessary, you can leave one blank line after the summary and then
   provide a more detailed description.

4. **Reference related issues:** If the commit is related to an issue in
   your GitHub project, reference this issue in the commit message. This
   helps to link your commits and the issues they resolve (e.g., "Add
   function to compute averages, closes #42").

5. **Be clear and descriptive:** While brevity is important, clarity
   should not be compromised. Ensure that you and others can understand
   the changes from the commit message.

Following these best practices will make your commit history clear and
easy to navigate for all contributors.

It's a good idea to prefix your commit messages with the type of change
you're making, especially when working in larger teams. This helps
provide more context at a glance when looking at the commit history.
Here are some examples based on different types of branches:

1. **Feature Branch:** When you're adding a new feature, your commit
   message could start with `FEATURE:`. This indicates that the commit
   adds new functionality to the project.

   Example: `FEATURE: Add function to compute averages`

2. **Bug Branch:** If you're fixing a bug, you could start your commit
   message with `BUG:`. This makes it clear that the commit is related
   to bug fixing.

   Example: `BUG: Fix error in average computation function`

3. **Documentation Branch:** When you're updating documentation, you can
   prefix your commit message with `DOCS:`. This shows that the commit
   changes are documentation-related.

   Example: `DOCS: Update contributing guidelines`

4. **Refactor Branch:** If you're refactoring existing code without
   changing its functionality, you could use `REFACTOR:` as a prefix.

   Example: `REFACTOR: Simplify average computation function`

5. **Test Branch:** When you're adding or changing tests, you can use
   the prefix `TEST:`.

   Example: `TEST: Add unit tests for average computation function`

These prefixes are not mandatory, but they are a good way to keep your
commit messages informative and organized. They can be particularly
useful in projects with many contributors, as they allow you to quickly
scan through the commit history and identify the type of changes made in
each commit.

## 5. Pull Request Review Process

Pull requests are a vital part of our workflow. They allow us to
collaboratively review and discuss changes made in a branch before they
are merged into the main branch. This ensures the quality of the code
and helps maintain a cohesive and robust codebase.

When a pull request is opened, it is assigned to another data scientist
for review. The reviewer's role is to thoroughly understand the proposed
changes, evaluate them, and provide constructive feedback. Below is the
step-by-step process:

1. **Understand the Changes**: Begin by reading the pull request
   description. This should give you a good understanding of what the
   proposed changes are and why they were made. If the description is
   not clear or if you have any questions, ask the author of the pull
   request to clarify.

2. **Review the Code**: Go through the changed files and lines of code
   in the pull request. Look for any potential issues or improvements.
   This could include bugs, performance issues, readability issues,
   unnecessary complexity, or deviation from our coding standards and
   practices.

3. **Run the Code**: Check out the branch on your local machine and run
   the code. Verify that it works as expected and achieves the intended
   purpose.

4. **Go Through the Checklist**: Use the provided checklist in the pull
   request template to ensure all our standards are met. This includes
   areas like data preparation, feature engineering, model building,
   code quality, and documentation. Make sure each item is checked off
   and the code meets the requirements.

5. **Provide Feedback**: If you find any issues or have suggestions for
   improvement, provide feedback in the form of comments. Be specific
   and clear in your feedback, and always be respectful and
   constructive. Remember, the goal is to improve the code, not to
   criticize the author.

6. **Approve or Request Changes**: If you're satisfied with the changes
   and all checklist items are met, approve the pull request. If there
   are issues that need to be addressed, select "Request changes" and
   summarize your feedback in the review summary.

The author of the pull request will address your feedback and make
necessary changes. Once you're happy with the updates, approve the pull
request. 

Once approved by the reviewer, and all continuous integration and checks
pass, the pull request can be merged into the main branch. 

Remember, the goal of the pull request review process is to ensure that
we're consistently improving our codebase and maintaining high standards
of quality. This collaborative process not only leads to better code,
but also provides an opportunity for team members to learn from each
other.

### Deciding When to Merge or Keep a Branch Separately

During the Pull Request review process, one important decision to make
is determining when a branch should be merged into the main branch, and
when it should be kept separately for documentation purposes. This
decision should be based on the nature of the changes made in the branch
and the impact they have on the overall project.

Here's a brief guideline on how to make this decision, based on the
[branch types
document](https://github.com/dslp/dslp/blob/main/branching/branch-types.md)
from the Data Science Lifecycle Process:

1. **Bug, Hotfix, and Release branches:** These branches are typically
   created to fix errors, make urgent changes, or prepare for a new
   version release of the project. As such, once the changes have been
   reviewed and approved, these branches should generally be merged into
   the main branch to ensure the project is up-to-date.

2. **Feature branches:** These branches are created to implement new
   functionality into the project. If the feature has been completed and
   properly tested, and the team agrees it adds value to the project,
   the branch should be merged into the main branch.

3. **Data and Model branches:** These branches are used to acquire new
   data or build and test new models. The decision to merge these
   branches can depend on the outcomes. If the new data or models
   improve the project significantly, merging could be the right
   decision. However, if they don't add substantial value, they could be
   kept separately as documentation of the process and outcomes.

4. **Experiment branches:** These branches are generally used for
   exploratory work, testing new ideas or approaches without affecting
   the main project. As these branches are more about learning and
   discovery, they are typically not merged into the main branch.
   Instead, they should be kept as separate records of the experiments
   conducted and the findings.

5. **Docs branches:** These branches are dedicated to updating
   documentation, instructions, or other non-code files. If the updates
   are relevant and necessary for the team or users, these branches
   should be merged into the main branch.

Remember, these are general guidelines and each decision should be made
considering the specifics of your project and the changes made in each
branch. The key is to maintain a clean, efficient, and accurate main
branch that represents the current state of your project.

## 6. Review and Merge Using GitHub

In the context of data science projects, reviewing a pull request is a
critical stage where another data scientist verifies the code, checks
for potential bugs, ensures the code aligns with project standards, and
confirms that the proposed changes meet the requirements defined in the
issue.

To facilitate this process, we recommend watching this instructional
YouTube video: [How to Review a Pull Request on
GitHub](https://youtu.be/lSnbOtw4izI). This video provides a detailed
walkthrough of the review process, demonstrating how to navigate the
GitHub interface, how to examine the changes made in a pull request, how
to leave useful comments, and how to approve or request changes.

Key points covered in the video include:

1. **Navigating to the pull request:** The reviewer needs to go to the
   'Pull requests' tab in the project repository and select the pull
   request they have been assigned to review.

2. **Understanding the changes:** The 'Files changed' tab gives an
   overview of what has been altered. The reviewer should carefully read
   through the proposed changes, keeping an eye out for potential issues
   and areas for improvement.

3. **Leaving comments:** If the reviewer spots a potential issue or has
   a suggestion, they can leave comments directly on the lines of code
   in question. These comments should be clear, concise, and
   constructive.

4. **Requesting changes:** If there are issues that need to be addressed
   before the pull request can be merged, the reviewer can use the
   'Review changes' button to request changes. This provides an
   opportunity to summarize the required changes and give overall
   feedback.

5. **Approving the pull request:** If the reviewer is satisfied with the
   changes, they can use the 'Review changes' button to approve the pull
   request. Once approved, the pull request can be merged into the main
   branch.

Remember, the goal of the review process is to ensure that the quality
of the codebase is maintained and that the changes align with the
project's objectives. It's also an opportunity for team members to learn
from each other and to maintain a clear and structured workflow.

## 7. Close the Issue

After your pull request has been reviewed and the changes have been
merged into the main branch, it's time to close the issue. Closing an
issue signifies that the work described in the issue has been completed
and no further action is needed.

Here's how you can close an issue on GitHub:

1. **Go to the issue:** In your repository, navigate to the 'Issues' tab
   at the top of the page. Locate the issue that you've been working on.

2. **Check the issue:** Before closing an issue, it's important to
   ensure that all the tasks and objectives outlined in the issue have
   been completed. Make sure that your merged pull request has fully
   addressed the issue's goals.

3. **Close the issue:** If everything is in order, you can proceed to
   close the issue. To do this, scroll down to the bottom of the issue
   page and click the 'Close issue' button.

4. **Comment before closing (optional):** It's often a good practice to
   leave a final comment summarizing the work that's been done,
   particularly if the issue discussion has been extensive. This can
   include a brief summary of the changes made, the pull request that
   resolved the issue, or any other relevant information. After leaving
   your comment, click on the 'Comment and close' button.

5. **Confirm the issue is closed:** Once an issue is closed, it will be
   labeled as 'Closed' and it will move from the 'Open' issue list to
   the 'Closed' issue list. You can always reopen it if further work or
   adjustments are required.

Remember, closing an issue is an important step in maintaining an
organized and efficient workflow. It allows team members to have a clear
understanding of what work has been completed, and it keeps your project
board clean and up-to-date.

## Appendix

### Using Labels on Issues and Pull Requests

Labels on issues and pull requests play a crucial role in managing and
organizing your project on GitHub. Here's why:

1.  **Improved organization and prioritization**: Labels categorize your
    issues and pull requests based on their purpose, status, or
    relevance. This makes it easier for you and your team to prioritize
    work.
    
2.  **Efficient filtering**: With labels, you can quickly filter and
    find specific issues and pull requests. You can even filter by
    multiple labels to narrow down your search further.
    
3.  **Enhanced communication**: Labels can communicate the status,
    priority, or type of issue or pull request to collaborators, leading
    to more effective project management and collaboration.

#### Default and Custom Labels

Here's a list of the default labels that GitHub provides, along with the
custom ones added for this project:

| Name | Description | Color | Type |
| --- | --- | --- | --- |
| bug | Something isn't working | d73a4a | Default |
| documentation | Improvements or additions to documentation | 0075ca | Default |
| duplicate | This issue or pull request already exists | cfd3d7 | Default |
| enhancement | New feature or request | a2eeef | Default |
| good first issue | Good for newcomers | 7057ff | Default |
| help wanted | Extra attention is needed | 008672 | Default |
| invalid | This doesn't seem right | e4e669 | Default |
| question | Further information is requested | d876e3 | Default |
| wontfix | This will not be worked on | ffffff | Default |
| ask | Define and scope problem and solution | c9ecff | Custom |
| explore | Explore and document data to increase understanding | f0f29b | Custom |
| experiment | Build features and train models | 8569c6 | Custom |
| data | Get and transform data | 1c587c | Custom |
| model | Prepare model for deployment | 0b4e82 | Custom |
| deploy | Register, package, and deploy model | f79499 | Custom |
| communicate | Write reports, create dashboards, summarize findings, etc. | f9f345 | Custom |
| succeeded | This was successful | 67d157 | Custom |
| failed | This didn't go as hoped | c2021c | Custom |
| onhold | Still seems promising, but let's revisit later | ffd04f | Custom |
| blocked | Blocked due to lack of access to data, resources, environment, etc. | ed9a53 | Custom |

#### Creating Labels Manually Using GitHub's Web Interface

If you prefer, you can also create labels directly through GitHub's web
interface:

1.  Navigate to your repository on GitHub.    
2.  Click on `Issues` in the repository navigation bar.
3.  Click on `Labels`.
4.  Click on `New label`.
5.  Fill out the `Label name`, `Description`, and `Color` fields.
6.  Click on `Create label`.
   
You can repeat steps 4-6 to create as many labels as you need. While
this method is more manual and time-consuming than using GitHub CLI, it
can be a good option if you're not comfortable using the command line or
if you only need to create a few labels.

#### Using GitHub CLI to Create Labels

The GitHub CLI is a powerful tool that allows you to interact with
GitHub directly from your command line. One of its features is the
ability to create labels. Here's how you can do it:

1. Open your text editor and paste the following into it:

```bash
#!/bin/zsh

gh label create ask --description "Define and scope problem and solution" --color c9ecff
gh label create explore --description "Explore and document data to increase understanding" --color f0f29b
gh label create experiment --description "Build features and train models" --color 8569c6
gh label create data --description "Get and transform data" --color 1c587c
gh label create model --description "Prepare model for deployment" --color 0b4e82
gh label create deploy --description "Register, package, and deploy model" --color f79499
gh label create communicate --description "Write reports, create dashboards, summarize findings, etc." --color f9f345
gh label create succeeded --description "This was successful" --color 67d157
gh label create failed --description "This didn't go as hoped" --color c2021c
gh label create onhold --description "Still seems promising, but let's revisit later" --color ffd04f
gh label create blocked --description "Blocked due to lack of access to data, resources, environment, etc." --color ed9a53
```

2.  Save this file as `create_labels.sh` in the directory of your
    choice.    
3.  Open Terminal and navigate to the directory where you saved the
    script.
4.  Run the following command to make your script executable:

```bash
chmod +x create_labels.sh
```

5.  Run the script with the following command:

```bash
./create_labels.sh
```

Your terminal will then execute each command in the script in sequence.
Make sure that you are in the root directory of the git repository where
you want these labels to be added.

For further information, refer to the following resources:

- [Managing
  labels](https://docs.github.com/en/github-ae@latest/issues/using-labels-and-milestones-to-track-work/managing-labels)
- [gh label create](https://cli.github.com/manual/gh_label_create)
- [GitHub CLI](https://cli.github.com/)
- [Creating and Adding Labels to GitHub Pull Requests and
  Issues](https://www.blinkops.com/blog/creating-and-adding-labels-to-github-pull-requests-and-issues)

### Security Best Practices While using Google CoLab

Google Colab is a widely used tool for data analysis, machine learning,
and more, but like all computing environments, it's important to follow
best practices for security. Here are some guidelines:

1. **Do Not Share Sensitive Information**: Avoid hardcoding sensitive
   data such as passwords, API keys, or personal information directly in
   your notebooks. If you need to use such information, consider using
   environment variables or Google Colab's secret manager feature.

2. **Clear Outputs**: Before sharing your notebook, ensure to clear
   outputs that may contain sensitive data. This is especially important
   if you're working with private datasets or displaying information
   that could be sensitive.

3. **Mount Google Drive Cautiously**: When you mount your Google Drive,
   your notebooks will have access to all of your files. Be careful
   about what operations you perform, especially with unfamiliar code,
   to avoid unwanted changes to your files. Also, unmount your Drive
   when you're done using it.

4. **Be Careful with External Code**: Avoid running code that you do not
   trust. Malicious code could potentially access your data or use your
   Colab instance for nefarious purposes.

5. **Run in Private Browsing / Incognito**: To further secure your data,
   consider running Colab in a private browsing or incognito window.
   This can help prevent other websites from accessing data from your
   Colab session.

6. **Regularly Check for Updates**: Google periodically updates Colab
   and its security features. Regularly check for updates to ensure that
   you're using the most secure version.

7. **Use Access Controls**: If you're sharing notebooks, make sure to
   use Google Drive's built-in access controls. You can set your
   notebooks to be viewable or editable only by specific people, people
   within your organization, or make them public, as necessary.

8. **Understand Sharing Risks**: When you share a notebook, the
   recipient can make a copy and modify it. They won't have access to
   your Google Drive unless you explicitly share the drive with them.

Remember, security is a continuous process and requires awareness and
good practices to prevent data breaches and maintain data integrity.

### Why it is not Possible to Use Google Colab with VS Code

The aproach cobining Google Colab, GitHub and VS Code described in the
[How to Connect to VSCode to
Colab](https://colab.research.google.com/github/JayThibs/jacques-blog/blob/master/_notebooks/2021-09-27-connect-to-colab-from-local-vscode.ipynb)
is not longer possible because:

_⚠️ Unfortunately, Google Colab recently prohibited the usage of SSH on
their platform. Using this library may restrict your ability to use
Colab in the future. Learn more in [Google Colab
FAQ](https://research.google.com/colaboratory/faq.html#limitations-and-restrictions)._

[ref](https://github.com/WassimBenzarti/colab-ssh).

Due this SSH usage limitation, it is only possible to use Google Colab
with GitHub but VS Code cannot be used to replace Colab notebooks.

### Working with Data and Colab

This [External data: Local Files, Drive, Sheets, and Cloud
Storage](https://colab.research.google.com/notebooks/io.ipynb#scrollTo=eikfzi8ZT_rW)
notebook summarize how to work with data and Google Colab.

#### Uploading files from your local file system

`files.upload` returns a dictionary of the files which were uploaded.
The dictionary is keyed by the file name and values are the data which
were uploaded.

```python
from google.colab import files

uploaded = files.upload()

for fn in uploaded.keys():
  print('User uploaded file "{name}" with length {length} bytes'.format(
      name=fn, length=len(uploaded[fn])))
```

#### Downloading files to your local file system

`files.download` will invoke a

```python
from google.colab import files

with open('example.txt', 'w') as f:
  f.write('some content')

files.download('example.txt')
```
