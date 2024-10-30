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

## Introduction to YAML:
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
