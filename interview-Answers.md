## Azure DevOps Interview Questions

Most Azure DevOps interviews focus primarily on the **Azure DevOps Pipeline service**.

Azure DevOps consists of five services:
- Azure Boards
- Azure Repos
- Azure Pipelines
- Azure Artifacts
- Azure Test Plans

---

### Azure Boards
Azure Boards is similar to project management tools like Jira.

- Common topics:
  - What is Agile?
  - What is Kanban?

> **Note:** I will add specific questions on Azure Boards later. You might be asked one or two questions.

---

### Azure Repos
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

### Azure Pipelines

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
- How do you connect Azure Cloud from an Azure DevOps pipeline?
- What are the differences between Classic Pipelines and YAML Pipelines?
- What is the difference between a build pipeline and a release pipeline?  
  > *Note:* This is relevant in Classic Pipelines. In YAML pipelines, build and release are integrated.

- What are the different types of **hosted agents** in Azure DevOps for CI/CD?
- How can you pass variables between pipeline stages?
- What is a pipeline artifact, and how do you use it?
- How do you implement conditional execution of steps or jobs?
- How do you implement approval gates in a pipeline?
- How can you set up deployment to different environments (Dev, QA, Prod)?
- What are service connections, and how do you use them?  
  - What are the different types of **service connection** configurations?
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

### Azure Artifacts

Only a few questions are asked on Azure Artifacts in interviews.

- What is the purpose of Azure Artifacts?
- What is the difference between an Azure Pipeline artifact and an application artifact in the Azure Artifacts service?
- How can we clone dependencies from Azure Artifacts?

---

### Azure Test Plans

Relevant mostly to QA engineers; fewer questions are asked in DevOps interviews.

- What is Azure Test Plans, and where does it fit in the Azure DevOps ecosystem?
- What types of testing can you manage using Azure Test Plans?
- What are the key components of a test plan in Azure DevOps?
- What is the difference between test plans, test suites, and test cases?
- How do you create a manual test case in Azure Test Plans?
