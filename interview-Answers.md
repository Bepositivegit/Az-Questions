## Azure DevOps Interview Questions

Most Azure DevOps interviews focus primarily on the **Azure DevOps Pipeline service**.

1. **What is Azure DevOps?**  
   *Answer:* Azure DevOps is a cloud-based DevOps platform providing CI/CD pipelines, version control, testing, and deployment automation.

2. **What are the core components of Azure DevOps?**  
   *Answer:* Azure DevOps consists of five services:  
   - Azure Repos – Version control  
   - Azure Pipelines – CI/CD automation  
   - Azure Artifacts – Package management  
   - Azure Test Plans – Testing framework  
   - Azure Boards – Agile project tracking  

---

## Table of Contents
- [Azure Boards](#azure-boards)
- [Azure Repos](#azure-repos)
- [Azure Pipelines](#azure-pipelines)
- [Azure Artifacts](#azure-artifacts)
- [Azure Test Plans](#azure-test-plans)

---

## Azure Boards

Azure Boards is similar to project management tools like Jira.

- **Common topics:**
  - What is Agile?
  - What is Kanban?

> **Note:** I will add specific questions on Azure Boards later. You might be asked one or two questions.

---

## Azure Repos

Azure Repos is similar to GitHub.

**Common questions:**
- **How is Azure Repos different from GitHub or Bitbucket?**  
  *Answer:* There is no functional difference. Azure Repos is part of the Azure DevOps ecosystem. All three serve the purpose of acting as a **Git remote repository**.

- **What are the two types of version control supported in Azure Repos?**  
  *Answer:* Git and TFVC (Team Foundation Version Control – Centralized Version Control).  
  > *Note:* If asked whether you have experience with TFVC, it's okay to say no. It's not commonly used.

- **How do you clone a repository from Azure Repos?**  
  *Answer:* Two methods:  
    a. Username and password  
    b. SSH method

- **How can you enforce branch policies in Azure Repos?**  
  *Answer:*  
  Go to your Azure DevOps project → Repos → Branches.  
  Hover over your branch (e.g., `main`) → click the ellipsis (⋯) → Branch policies.  
  Configure policies like:  
  - Minimum number of reviewers  
  - Required build validation  
  - Check for linked work items  
  - Merge strategy  

- **How do you manage access and permissions for Azure Repos?**  
- **What is a repository policy, and how do you apply one?**  
- **How can you restrict force-pushes or direct commits to protected branches?**  
- **What is the purpose of *pull request templates*?**

---

## Azure Pipelines

**Common questions:**
- **I have code in GitHub, and I need CI/CD with Azure Pipelines. How can you do that?**  
  *Answer:* Create a service connection to connect GitHub.  
  At the time of creating the pipeline, modify the Git remote repository to point to **GitHub**.

- **What is an Azure Pipeline?**  
  *Answer:* Azure Pipelines is a CI/CD service that automates software build, test, and deployment.

- **What is the difference between Pipelines and Classic Pipelines?**  
  *Answer:*  
  - Pipelines: Code-based, version-controlled.  
  - Classic Pipelines: GUI-based, easier setup.

- **How do you define a pipeline using YAML?**  
  *Answer:*  
  ```yaml
  trigger:
    branches:
      include:
        - main
  stages:
    - stage: Build
      jobs:
        - job: BuildJob
          steps:
            - script: echo "Build step"
