## Azure DevOps Interview Questions

Most Azure DevOps interviews focus primarily on the **Azure DevOps Pipeline service**.

Azure DevOps consists of five services:
- Azure Boards
- Azure Repos
- Azure Pipelines
- Azure Artifacts
- Azure Test Plans

---
## Table of Contents
- [Azure Boards](#azure-boards)
- [Azure Repos](#azure-repos)
- [Azure Pipelines](#azure-pipelines)
- [Azure Artifacts](azure-artifacts)
- [Azure Test Plans](azure-test-plans)

---

## Azure Boards
Azure Boards is similar to project management tools like Jira.

- Common topics:
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
- I have code in GitHub, and I need CI/CD with Azure Pipelines. How can you do that?  
  *Answer:* Create a service connection to connect GitHub.  
  At the time of creating the pipeline, modify the Git remote repository to point to **GitHub**.

- What is the basic structure of Azure DevOps YAML?  
  *Answer:* A pipeline starts with:  
  - `trigger`: Specifies the branches that will trigger the pipeline.  
  - `pool`: Specifies the agent OS to run the pipeline.  
  - `variables`: Defines pipeline-wide variables.  
  - `stages`: Logical groupings of jobs (e.g., Build, Test, Deploy).  
  - `jobs`: Part of a **stage**. A collection of steps that run on the same agent.  
  - `steps`: Part of a **job**. Actual tasks or scripts that get executed.

- What is the difference between **parameter** and **variable** in Azure DevOps YAML?  
  *Answer:* If we require variable types like **boolean**, **string**, **number**, or **object**, we declare them as **parameters**.  
  - In the case of **variables**, the type is always treated as a **string**.  
  - Parameter values are evaluated **before** the pipeline starts (at compile time), while variable values can be changed **during** pipeline execution (at runtime).

- How do you connect Azure Cloud from an Azure DevOps pipeline?
  * Answer:* by creating __servie connection__ in azure devops
- What are the differences between Classic Pipelines and YAML Pipelines?
  *Answer:* 
  -  Use Classic if you prefer a UI or are just starting with CI/CD in Azure DevOps.
  - Use YAML if you want pipelines as code, better maintainability, and CI/CD versioning within your repo.

- What is the difference between a build pipeline and a release pipeline?
  * Answwer:* A build pipeline compiles and unit testing, static code anaysis, push artifact to artiact reposioty, while a release pipeline deploys the built code to environments.  

- What are the different types of **hosted agents** in Azure DevOps for CI/CD?
 * Answer:*
 - Microsoft hosted agents: these are managed by Azure devops
 - Selfhosted agents: we need to add our __VM__'s to azure devops, to run the pipelines on those VM's
- How can you pass variables between pipeline stages?
  * Answer:* we can do with two ways
   - define variable in the pipeline, call it
   - atach __varibale group__ to the pipeline, __variable group__ contain the list of key and value pairs
- What is a pipeline artifact, and how do you use it?
 * Answer:* After build the applicaiton, we will store applicaiton artifact inside the pipeline and publishing to use at the deployment. That why we are calling as __pipeline artifact__.
- How do you implement conditional execution of steps or jobs?
* Answer:* by using __condition keyword__. The below are the list of conditions
  - succeeded(): Runs if the previous step or job succeeded.
  - failed(): Runs if the previous step or job failed.
  - always(): Runs regardless of whether previous steps or jobs succeeded or failed.
  - canceled(): Runs if the previous step or job was canceled.
  - eq(): Checks if two values are equal (e.g., eq(variables['Build.SourceBranch'], 'refs/heads/main')).
  - ne(): Checks if two values are not equal.
  - and(): Combines multiple conditions to run when all are true.
  - or(): Combines multiple conditions to run when any are true.

- How do you implement approval gates in a pipeline?
  * Answer:* Approval gates in a pipeline are implemented using the Environment resource in Azure DevOps, where manual or automated approvals are required before progressing to the next stage or job.

- How can you set up deployment to different environments (Dev, QA, Prod)?
  *Answer:* creating __multi-stage__ YAML pipelines with separate stages for each environment, and using environment-specific variables and __approval gates__ for controlled deployments.

- What are service connections, and how do you use them?  
  *Answer:* Service connections in Azure DevOps are secure connections to external services or resource like, AWS, Azure, etc
- In how many ways of **service connection** configurations?
- How do you secure secrets and sensitive information in pipelines?
- How can you integrate Azure Key Vault with Azure DevOps to fetch secrets?
- What scripting languages can be used in Azure Pipelines?
- How do you use templates to modularize your YAML pipeline?  
  > *Note:* This relates to the shared library concept.

- How do you enforce pipeline policies or permissions for contributors?

- Most Azure DevOps projects use **.NET applications**. What are the steps to build a .NET application?
- How can we integrate **SonarQube** with Azure DevOps pipelines?
- What tools do you use or know about for identifying **security vulnerabilities** in software? How do you integrate them with Azure DevOps?

- **Important:** Do you have experience with Azure AKS? How do you deploy an application to Azure AKS using Azure DevOps?  
  > *Note:* Interviewers expect detailed steps for this scenario.

- If we have an application to deploy to Azure AKS and it requires **sensitive information** from Azure Key Vault, what are the detailed steps to configure this in Azure DevOps and Azure AKS?

- For services like Azure Cloud, Azure App Service, Azure VM, and Azure AKS, it's good to remember detailed CI/CD steps.

- What is the difference between **System-Managed Identity** and **User-Managed Identity** in Azure?  
  > *Note:* Sometimes asked in Azure DevOps interviews.

- How do you deploy an application to production only after manual approval?

- What is the purpose of **Environments** in Azure DevOps?

---

## Azure Artifacts

Only a few questions are asked on Azure Artifacts in interviews.

- What is the purpose of Azure Artifacts?
- What is the difference between an Azure Pipeline artifact and an application artifact in the Azure Artifacts service?
- How can we clone dependencies from Azure Artifacts?

---

## Azure Test Plans

Relevant mostly to QA engineers; fewer questions are asked in DevOps interviews.

- What is Azure Test Plans, and where does it fit in the Azure DevOps ecosystem?
- What types of testing can you manage using Azure Test Plans?
- What are the key components of a test plan in Azure DevOps?
- What is the difference between test plans, test suites, and test cases?
- How do you create a manual test case in Azure Test Plans?
