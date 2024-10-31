## CI/CD leraning tutorial

**Overview**: The course, focuses on Continuous Integration/Continuous Delivery (CI/CD) techniques specifically for Machine Learning (ML).
**SDLC Overview**:
SDLC (Software Development Life Cycle) involves stages like building, testing, and deploying software.
**SDLC in Machine Learning**:
ML workflows require data and model versioning and comprehensive testing across the ML pipeline.
ML development has unique challenges, including ongoing data updates and data engineering needs.
**Build**: Converts source code to executable code.
**Test**: Validates functionality and quality.
**Deploy**: Makes software available for use.
**SDLC in Machine Learning**:
ML development has unique challenges, including ongoing data updates and data engineering needs.
CI/CD integration in ML helps streamline development, accelerate iteration, and enable rapid prototyping and testing.
### CI/CD Concepts:
**Continuous Integration (CI)**: Automates building and testing code changes in a shared repository to avoid integration issues.
**Continuous Delivery (CD)**: Automates delivery of code changes to production with manual approvals.
**Continuous Deployment (CD)**: Extends Continuous Delivery by fully automating deployments.
**CI/CD in Machine Learning:**
ML workflows require data and model versioning and comprehensive testing across the ML pipeline.
Unique ML needs include tracking experiments, managing model infrastructure, and monitoring model performance.
CI/CD in ML also addresses the complexities of model reproducibility, pipeline testing, and streamlined deployment.
**Scope**: Covers data preparation, versioning, model development, evaluation, and hyperparameter tuning within CI/CD frameworks.
**Summary**: Highlights the benefits of CI/CD in ML, including automation, reproducibility, enhanced testing, and efficient, reliable deployment.

### Introduction to YAML:
YAML is a human-readable data format used widely for configuration files, data exchange, and structuring data in applications.
It provides an alternative to XML and is similar in function to JSON, aiming to facilitate interoperability across languages and applications.
YAML files use .yaml or .yml extensions and are heavily utilized in CI/CD tools, such as GitHub Actions and Data Version Control, to define workflows.
**YAML Syntax:**
YAML relies on consistent indentation (using spaces, not tabs) and line separation to organize data hierarchies.
Incorrect indentation leads to syntax errors, so using YAML validation tools is recommended.
Comments start with #.
**YAML Scalars:**
Scalars in YAML include data types like strings, numbers, booleans, and null values.
Boolean values are true or false without quotes, and null is represented by null or ~.
Strings can be unquoted, single-quoted, or double-quoted.
**YAML Collections:**
Collections consist of sequences (ordered lists) and mappings (key-value pairs).
Sequences are written in block style (with hyphens) or flow style (within brackets).
Mappings use a key-value structure, represented by a colon and can contain various data types.
Summary:
YAML is essential for CI/CD configuration, especially in ML applications, due to its readability and structure.
YAML relies on mappings, sequences, and scalars for data organization.
**Editor Exercises Layout:**
The editor layout includes folders (pink box), open files (blue box), and a terminal for bash commands (green box).


### Introduction to GitHub Actions:
GitHub Actions (GHA) is a popular CI/CD platform used for automation in software development. **What is GitHub Actions?:**
GHA is an integrated automation and CI/CD system within GitHub that automates build, test, and deployment pipelines in repositories.
The "pipeline" represents a sequence of interconnected steps or stages in the development process.
**Analogy with Car Assembly Line:**
GHA automates software development processes like tasks in a car assembly line, ensuring efficient workflow.
**Automated Steps:**
Developers can create automated steps for tasks like code building, testing, and deployment, mirroring the sequential process of an assembly line.
**GHA Components:**
Event: An action within a repository (e.g., pull request, issue creation, commit push) that triggers a workflow.
**Workflow:**
A customizable automated process defined in a YAML file, which can execute multiple jobs. Workflows are stored in the .github/workflows directory and can be triggered by events, manually initiated, or scheduled.
**Steps and Actions:**
Steps: Individual units of work executed sequentially, dependent on previous steps, sharing data on the same compute machine.
**Actions:**
Custom applications for complex tasks, such as checking out a repository or commenting on pull requests.
**Jobs and Runners:**
Job: A set of steps in a workflow that can run independently and in parallel. Jobs are executed on compute machines called runners.
**simple GHA Workflow Example:**
A push event can trigger a workflow where a job runs on an Ubuntu Linux runner, performing two steps: checking out the repository and running a Python application.
**Overview of Components:**
A GitHub repository contains a workflow file in the .github/workflows directory, defining the workflow triggered by events (like pushes or pull requests). The workflow can execute multiple jobs, which are made up of steps, allowing various actions or scripts to run on the same runner machine and optionally produce output artifacts.


**Introduction to Intermediate YAML:**
The focus is on expanding understanding of YAML for effective use with GitHub Actions.
Multiline Strings:
**Block Scalar Format:**
Multiline strings can be represented using Block Scalar Strings, which preserve formatting (line breaks and indentation).
Useful for code snippets, log messages, and configurations in ML CI/CD workflows.
**Style Indicators:**
Literal Style: Preserves line breaks and indentation, ideal for writing shell commands.
**Example:**
Shows how literal style maintains new lines and indentation, except for the last line controlled by chomping indicators.
**Fold Style:**
This style removes line breaks, converting them into spaces for better readability.
**Example:**
Demonstrates how fold style collapses line breaks but preserves breaks followed by blank lines.
**Chomping Indicators:**
Special instructions that dictate whether to keep or remove extra blank lines at the end of multiline text.
**Default Mode (Clip):**
Adds a single newline at the end without needing a symbol.
**Strip Indicator:** 
Removes all newlines at the end of the block.
**Keep Indicator:** 
Retains all newlines at the end.
**Dynamic Value Injection:**
Although not standard in YAML, expressions serve as placeholders for dynamic values that change during processing.
Typically formatted with curly braces and a leading dollar sign (e.g., ${value}).
Allows referencing environment variables or other YAML fields but may not be supported by all parsers.
**Multi-document YAML:**
Allows storing multiple independent YAML documents within a single file, separated by three dashes (---).
Useful for organizing related documents together. Each document is a complete YAML structure.**Summary:**
Review of the symbols covered, emphasizing that chomping indicators follow style indicators in YAML.

### CI Pipeline
**Introduction to CI Pipeline:**
The video covers setting up a continuous integration (CI) pipeline using GitHub Actions.Components of GitHub Actions Workflow:
Define the workflow name (e.g., "CI").
Specify events that trigger the workflow, such as pushes to the main branch using the on: push block.
**Jobs in Workflows:**
A workflow consists of one or more jobs that can run sequentially or in parallel.
Define a job called "build" that runs on compute machines (runners) specified by the runs-on field.
Indentation is important for defining the structure.
Steps are defined using the steps field, which includes a multi-line echo command executed by the runner's shell.
**Creating a GitHub Repository:**
Create a new repository on GitHub by navigating to github.com/new.
Add a Python-based .gitignore file and an appropriate license before creating the repository.
**Enabling GitHub Actions:**
Ensure GitHub Actions are enabled in the repository by checking the settings at github.com/username/repository_name/settings/actions.
Setting Up a "Hello, World!" Action:
Click on "Actions" in the repository landing page to set up the first GitHub Action.
Search for a "Simple Workflow" and click "Configure" to create or edit a YAML file for the workflow.
**Creating the YAML Workflow:**
Workflows should be saved in the .github/workflows folder.
Create a YAML workflow to print "Hello, World!" and commit the changes.
**Triggering the Workflow:**
The commit message is entered, and clicking "Commit changes" kicks off the workflow.
**Inspecting the GitHub Actions Run:**
The commit SHA displays an amber circle (ongoing), green tick (successful), or red cross (failed).
In this case, the pipeline succeeded.
**Viewing Successful Workflows:**
Clicking "Actions" in the top menu shows the successful workflow.
Jobs in the workflow are listed, including the "build" job.
**Inspecting Job Logs:**
Clicking on the "build" job shows output logs from the steps, including the output of the echo commands and additional setup/cleanup steps.

### Configuring GitHub Actions:

**Triggering on Pull Request:**
The video demonstrates extending a GitHub Actions workflow to trigger on a pull request.
**Shared Repository Model:**
In collaborative repositories, feature or topic branches are created for individual changes.
Developers create pull requests for code review, allowing CI/CD tools to automatically test code quality, security, and compatibility, providing early feedback before merging to the main branch.
**Creating a Feature Branch:**
To create a feature branch, click "Branch" on the repository landing page, then "New branch" to name and activate the branch.
**Adding Code to the Repository:**
In the feature branch, add a Python script (e.g., hello_world.py) that prints a message and the current time, then commit it.
**Configuring Workflow Event:**
Modify the workflow event to trigger on pull_request instead of push.
Set the target branch (main) for the pull request where the code will merge.
**Actions Syntax:**
Actions are specified under the steps field with the uses key.
Syntax includes organization/username, repository name, and version number (e.g., @v3).
Additional arguments are defined using the with key. Actions are available in GitHub Marketplace and from private sources.
**Configuring Workflow Steps:**
Use separate steps to "Check out" the repository (checkout action) and set up the Python environment (setup-python action).
Specify the version of each action (e.g., checkout@v3, setup-python@v4) and select the Python version with python-version.
**Final Workflow:**
workflow uses on-pull_request as the event trigger.
It includes checkout and setup-python steps, followed by running the Python script.
Creating Pull Request and Running Workflow:
Commit changes to the feature branch, then create a pull request targeting the main branch.
The workflow triggers automatically, and clicking "Details" opens the logs page.
**Inspecting Workflow Logs:**
In the logs, view the checkout and setup-python steps along with the successful execution of the Python script.