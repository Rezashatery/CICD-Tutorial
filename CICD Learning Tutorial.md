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

### Environment Variables and Secrets in GitHub Actions:
**Contexts:**
Contexts in GitHub Actions provide predefined environment variables that contain information about the repository, workflow, event, and environment.
These contexts include github, env, secrets, job, and runner.
Contexts are accessed with double curly braces and a leading dollar sign, e.g., ${{ github }}.
**Variables:**
Variables in GitHub Actions are stored as plain text, suitable for non-sensitive data (e.g., compiler flags, usernames).
They can be declared using the env keyword in the YAML file and accessed via the env context.
Variable scope is determined by where they are declared (workflow, job, or step level).
**Secrets:**
Secrets are used for sensitive data (e.g., passwords, API keys) and are encrypted in storage.
Secrets are accessed using the secrets context and can be set in the YAML file under env or with keys.
GitHub Actions hides secret values from logs for security.
**Setting Secrets:**
To add a repository-level secret, go to Settings > Secrets and Variables in the repository, then click Actions > New Repository Secret.
**GITHUB_TOKEN Secret:**
GitHub provides a built-in GITHUB_TOKEN secret for every workflow run, allowing interaction with the GitHub API.
This token enables actions such as cloning the repository, managing issues and pull requests, and commenting.
The GITHUB_TOKEN permissions adjust automatically based on the workflow event, but permissions can also be customized as needed.
**Example: Commenting on a Pull Request:**
To comment on a pull request, permissions are elevated using permissions: pull-requests.
The GITHUB_TOKEN is used within the with key in an action (e.g., thollander/action-comment-pull-request) to post a comment.
This example shows the GitHub Actions bot adding a "Hello world" comment on the pull request.


### Model Training with GitHub Actions
The video demonstrates how to set up a GitHub Actions workflow to train machine learning (ML) models.
Dataset: Weather Prediction in Australia:
A binary classification dataset on Australian weather is used, with features including 5 categorical (e.g., location, wind direction, rain today) and 17 numerical (e.g., temperatures, wind speeds).
**Modeling Workflow:**
The workflow includes:
        ◦ Converting categorical to numerical data,
        ◦ Handling missing values,
        ◦ Standardizing features,
        ◦ Splitting data for training and testing,
        ◦ Training a Random Forest Classifier with fixed hyperparameters, and
        ◦ Reporting performance metrics like precision and recall.
**Data Preparation: Target Encoding:**
Target encoding is used for converting categorical variables by replacing feature values with their average in the target column, especially useful over one-hot encoding for large categorical features.
**Imputing and Scaling:**
Missing values are filled using the mean, and the data is scaled to zero mean and unit standard deviation.
**Training:**
The dataset is split into training and test sets using train_test_split, and a RandomForestClassifier model is trained for accuracy, robustness, and handling multiple features.
**Metrics:**
Key performance metrics reported are accuracy, precision, recall, and F1 score.
**Plots:**
A confusion matrix heatmap is generated to display true positives, false positives, true negatives, and false negatives.
**GitHub Actions Workflow:**
The model training workflow is triggered upon pull requests to the main branch.
Continuous Machine Learning (CML), an open-source tool for ML CI/CD, is used for provisioning, training, evaluation, and generating visual reports automatically for each pull request.
**CML Commands:**
The workflow YAML file initializes the setup-cml action, runs the training code, reads results from results.txt and a graph image, and writes them to a markdown file. This is posted as a comment on the PR with the cml comment create command and GITHUB_TOKEN.
**Output:**
The workflow, triggered by a pull request, posts a comment in the PR with model evaluation details.

### Versioning Datasets with Data Version Control (DVC):
This topic covers dataset versioning in machine learning projects, essential for tracking data changes, replicating training, and supporting collaboration.
**Why Versioning Data Matters:**
Data versioning enables:
    ◦ Replicating model training,
    ◦ Iterating on model architectures,
    ◦ Collaboration on consistent data,
    ◦ Diagnosing performance issues linked to specific datasets,
    ◦ Monitoring data changes requiring retraining, and
    ◦ Auditing data usage in regulated fields like finance and healthcare.
**Data Version Control (DVC):**
DVC is an open-source tool for versioning data, working similarly to Git but optimized for data. It allows unified management of code and data changes.
**DVC Storage:**
While Git tracks data versions, DVC stores actual data files remotely (e.g., via SSH, web APIs, cloud providers, or locally). DVC can be installed using pip.
**Initializing DVC:**
After initializing Git with git init, run dvc init to set up DVC, which creates files such as:
    ◦ .gitignore to exclude DVC files from Git,
    ◦ config for settings (e.g., remote storage), and
    ◦ tmp for cache and logs.
**Adding Files to DVC:**
Use dvc add <file> to track data files. This generates .dvc placeholder files containing metadata, allowing Git to version data indirectly. The DVC cache stores the actual data files.
DVC Data Files:
**.dvc files store metadata:**
    ◦ outs: Output data files,
    ◦ md5: MD5 checksum for integrity,
    ◦ size: File size in bytes,
    ◦ hash: Type of hash used (MD5), and
    ◦ path: File path (e.g., data.csv).
**Summary:**
DVC provides a lightweight, Git-integrated solution for data versioning. Initialize with dvc init, track files with dvc add, and use .dvc files for metadata and version control.

### DVC Remotes
**Interacting with DVC Remotes:**
This video explores DVC's capabilities for managing storage and accessing large datasets through external remotes.
**Understanding DVC Remotes:**
Git and GitHub face limitations for large data files, which DVC solves using external storage locations called DVC remotes. Benefits include:
    ◦ Syncing large files and directories,
    ◦ Creating a centralized data repository for collaboration,
    ◦ Archiving dataset and model versions while saving local storage.
Supported remotes include cloud providers like AWS, GCP, Azure, and on-prem storage options via SSH or HTTP.
**Setting Up Remotes:**
DVC remotes can be added with the dvc remote command, updating .dvc/config. For instance, an S3 bucket named "mybucket" can be added as a remote and customized with dvc remote modify. Settings are saved in .dvc/config.
**Local and Default Remotes:**
Local remotes offer fast access and control and are ideal for local testing. Options include system directories, network-attached storage, and external drives.
To set a default remote, use the -d flag with dvc remote add. Commands like dvc pull, dvc push, and dvc fetch will then use this default remote.
**Uploading and Retrieving Data:**
dvc push and dvc pull move data between remote storage and local workspace, analogous to git push and git pull. These commands support data sharing across environments and versioning of datasets, models, and metrics.
Data can be pushed for individual files or entire caches, with an option to specify remotes using -r. If unspecified, the default remote is used.
**Tracking Data Changes:**
For data updates:
    ◦ Use dvc add to stage changes in the DVC cache and update the corresponding .dvc file,
    ◦ Commit changes to Git with git add and git commit,
    ◦ Push metadata to Git with git push,
    ◦ Push the updated data file to the DVC remote with dvc push.


### DVC Pipelines


**DVC Pipelines Overview:**
DVC pipelines offer a structured way to reproduce machine learning (ML) workflows through a series of defined steps, or stages.
**Need for a Data Pipeline:**
In ML workflows, data needs processing (e.g., filtering, cleaning, transformation) before model training. DVC pipelines streamline this by allowing steps to be rerun only when dependencies change. This creates a dependency graph, or Directed Acyclic Graph (DAG), where each step depends on the output of the previous.
**DVC Pipelines Structure:**
DVC pipelines are defined in the dvc.yaml file, with stages including:
    ◦ deps (dependencies) such as raw data or scripts,
    ◦ cmd (command) to execute the stage,
    ◦ outs (outputs) like processed data, model artifacts, and metrics.
DVC pipelines can also integrate into GitHub Actions for workflow automation in ML projects.
**Defining Pipeline Stages:**
The dvc stage add command is used to create stages in dvc.yaml. Each stage specifies its name (-n), dependencies (-d), outputs (-o), and execution command.
**Dependency Graphs:**
Stages, like preprocessing and training, can be connected to form a dependency graph, with output from one stage serving as input for another.
**Reproducing a Pipeline:**
Using dvc repro, the pipeline is reproduced sequentially. A dvc.lock file is generated, capturing the pipeline state and is typically committed to Git to track current pipeline results.
**Caching Results:**
DVC skips unchanged steps during reruns, utilizing caching, which is especially beneficial for complex DAGs with multiple dependencies.
**Visualizing the Pipeline:**
The dvc dag command visualizes the pipeline stages as a connected graph, aiding in understanding workflow structure.
**Summary:**
DVC pipelines streamline ML workflows by identifying necessary steps for execution and using caching to avoid rerunning unchanged steps. Key files include dvc.yaml for pipeline setup and dvc.lock to log the current pipeline state, enabling CI/CD workflows in ML projects.



### Configuring Metrics in DVC YAML

**DVC for Tracking Metrics and Plots:**
DVC can track model performance metrics, visualize these metrics with plots, and compare performance across different experiments. This helps identify the best model for a machine learning task.
**Configuring Metrics in DVC YAML:**
To track metrics, specify the metrics file (e.g., metrics.json) under a metrics key in the dvc.yaml file (not under outs). Set cache: false to track this file with Git rather than DVC.
**Querying and Comparing Metrics:**
Use dvc metrics show to display metrics in the terminal and dvc metrics diff to compare metrics across experiments, e.g., after changing hyperparameters and rerunning dvc repro.
**Setting up DVC in GitHub Actions:**
Add setup-dvc GitHub Action for automated model comparisons. Replace Python scripts with the DVC pipeline commands and use dvc metrics show to print metrics as a markdown table in pull request comments.
**Pipeline Metrics in GitHub:**
Compare metrics to the main branch by fetching the main branch state and running dvc metrics diff. Generate a comment with Continuous Machine Learning (CML) to display results in pull requests.
**Plot Types Supported by DVC:**
DVC supports several plot types, including scatter plots, line plots, confusion matrices, and horizontal bar plots.
**Configuring Plots in DVC YAML:**
Track plot data files (not images) in dvc.yaml under plots, with templates for plot styles, axis labels, and column names. Setting cache: false for predictions files ensures tracking through Git.
**Generating and Comparing Plots:**
Use dvc plots show to generate plots (output as HTML with interactive features) and dvc plots diff to compare plot differences across branches.
**Comparing Specific Plots:**
Compare confusion matrices or ROC curves by specifying the target plot in dvc.yaml and the branch to compare it to. For ROC curves, calculate TPR and FPR using scikit-learn, then plot with a linear template.