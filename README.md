This the summerization of CI/CD tutorial. You can Find everything on the Tutorial.
Versioning Datasets with Data Version Control (DVC)
Importance of Data Versioning

Data versioning is critical in machine learning (ML) for:

    Replicability: Allows training to be reproduced accurately.
    Iteration: Facilitates testing of various models and architectures.
    Collaboration: Keeps data consistent for team collaboration.
    Diagnostics: Enables pinpointing dataset-specific performance issues.
    Retraining & Compliance: Monitors data changes and audits usage, crucial in fields like healthcare and finance.

Data Version Control (DVC) Overview

DVC, an open-source tool, version-controls datasets similarly to Git but optimized for large data files, separating the actual data storage from versioned metadata.
DVC Storage and File Structure

    Remote Storage: DVC stores data files in external storage (cloud providers, SSH, local).
    File Setup: Running dvc init sets up files for configurations and cache management.

Adding Data with DVC

Adding files with dvc add <file> generates .dvc metadata files in Git while storing data separately in the DVC cache. Metadata files include:

    outs: Output data files.
    md5: Checksum for data integrity.
    size: File size.
    path: Data file path.

DVC Remotes
Why Use DVC Remotes?

DVC remotes address Git limitations by storing large files externally, enabling:

    File Syncing: Efficiently manage large files.
    Central Repository: Streamlines collaboration.
    Local Space Optimization: Frees local storage by archiving versions remotely.

Remote Configuration

    Adding a Remote: Set up using dvc remote add, configured in .dvc/config.
    Using Remotes: Commands like dvc push and dvc pull move data between local storage and remote locations.
    Local Remotes: Ideal for rapid local testing and fast access.

DVC Pipelines
Why Pipelines in ML?

DVC pipelines simplify workflows by breaking them into reproducible steps (data cleaning, model training) defined as pipeline stages.
Defining Pipelines

    Pipeline Structure in dvc.yaml: Define each stage with deps (dependencies), cmd (execution command), and outs (outputs).
    Running Pipelines: dvc repro re-runs stages, updating only those with changed dependencies.
    Visualization: dvc dag generates a Directed Acyclic Graph (DAG) for pipeline steps, aiding workflow overview.

Configuring Metrics in DVC YAML
Tracking Model Performance Metrics

DVC supports tracking and visualizing metrics over model versions, ideal for comparing performance and identifying the best model.
Configuring Metrics

    Metrics in dvc.yaml: Metrics files (e.g., metrics.json) should use cache: false for Git tracking instead of DVC.
    Commands for Comparison: dvc metrics show for metric display; dvc metrics diff for comparing versions.
    GitHub Integration: Automatically generate metric tables in pull requests for easy comparison.

Plotting Capabilities

DVC supports various plot types (e.g., line plots, confusion matrices) for comprehensive analysis across experiments.
Hyperparameter Tuning
Importance of Hyperparameter Tuning

Tuning involves adjusting model parameters to optimize performance, typically performed independently of the main training workflow.
DVC YAML Configuration for Tuning

    Separate Stages: Define tuning and training as separate stages in dvc.yaml, depending on different datasets, scripts, or config files.
    Running Stages Individually: Use dvc repro <stage> to execute specific stages, re-running only dependent steps when required.
    Result Tracking: Outputs like scores or parameter sets are accessible via properties (e.g., cv_results in Grid Search).

Hyperparameter Tuning Workflow with DVC
Branching and GitHub Actions for Automation

Separating tuning and training stages in different branches allows workflows to run independently, avoiding unnecessary retraining.

    Branch Naming and Execution Control: In GitHub Actions, conditionally execute workflows based on branch prefixes (hp_tune/ for tuning, train/ for training).
    Automated PRs: DVC can automate pull request (PR) creation after successful tuning to start training on the full dataset.
    Manual Triggering: Training can be manually initiated by opening a PR from the appropriate train/ branch, useful for isolating stages and ensuring precise control.
