# 1. Sabse pehle basic concept samjho

Maan lo tumhe **Bhindi ki sabji** banani hai.

Do tarike ho sakte hain.

## Method 1: Kisi ko har step batana

```
1. Bhindi fridge se nikalo
2. Bhindi kato
3. Kadai lao
4. Gas chalu karo
5. Oil dalo
6. Pyaaz dalo
```

Yahan tum exactly bata rahe ho:

> **Pehle kya karna hai, phir kya karna hai.**

Is concept ko technical world mein bolte hain:

# **Imperative Approach**

---

## Method 2: Sirf final requirement batana

Tum bolte ho:

> "Bhai aaj Bhindi ki sabji bana lena."

Ab tumne individual steps nahi bataye.

Tumne sirf desired final result bataya:

> **Mujhe Bhindi ki sabji chahiye.**

Kaise banegi aur internal steps kya honge, implementation system/tool handle karega.

Is concept ko bolte hain:

# **Declarative Approach**

---

# 2. Technical Definition

## Imperative

**Imperative approach** mein hum system ko exact instructions dete hain ki task **kaise perform karna hai**.

### Focus:

> **HOW to achieve the result**

Example:

```
Step 1 → Resource Group create karo
Step 2 → Storage Account create karo
Step 3 → Network configure karo
Step 4 → VM create karo
```

---

## Declarative

**Declarative approach** mein hum desired end state define karte hain.

### Focus:

> **WHAT should exist**

Example:

```
Mujhe chahiye:

Resource Group = rg-prod
Location = Central India

Storage Account = mystorageaccount
SKU = Standard
```

Tool desired configuration ko read karta hai aur required resources create/manage karta hai.

---

# 3. Sabse important Interview Difference

|Imperative|Declarative|
|---|---|
|**How** batata hai|**What** batata hai|
|Step-by-step commands|Desired state define|
|Execution logic important|Final configuration important|
|Sequential commands|Configuration driven|
|Azure CLI common example|Terraform common example|
|Script-based automation|Infrastructure as Code|

---

# 4. Real Azure Example

Requirement:

> Hume Azure mein 4 Resource Groups create karne hain.

---

# Method 1: Manual Approach

Azure Portal open karenge.

Har Resource Group individually create karenge.

```
Resource Group 1 → Create
Resource Group 2 → Create
Resource Group 3 → Create
Resource Group 4 → Create
```

### Problem kya hai?

Agar requirement ho:

```
4 Resource Groups
20 Storage Accounts
15 VNets
100 Resources
```

To manually create karna:

- Time-consuming
- Human error
- Configuration inconsistency
- Difficult to reproduce
- Difficult to audit

---

# 5. Manual Infrastructure Management

Manual approach mein engineer Azure Portal use karta hai.

Example:

```
Azure Portal
        ↓
Create Resource Group
        ↓
Enter Name
        ↓
Select Subscription
        ↓
Select Region
        ↓
Review + Create
```

Ye approach small learning environments ke liye useful ho sakti hai.

Lekin production enterprise environment mein large-scale infrastructure ke liye manual creation generally preferred approach nahi hota.

### Why?

Because enterprise ko chahiye:

- **Consistency**
- **Repeatability**
- **Auditability**
- **Scalability**
- **Standardization**
- **Version Control**

---

# 6. Automation kya hoti hai?

Automation ka matlab:

> Repetitive manual tasks ko scripts ya tools ke through automatically perform karwana.

Infrastructure context mein example:

Instead of manually creating 4 Resource Groups:

```
Click
Click
Click
Click
```

Hum command/script/tool use karte hain.

---

# 7. Imperative Automation using Azure CLI

Azure CLI ek command-line tool hai jo Azure resources ko commands ke through manage karne ke liye use hota hai.

Example conceptual command:

```
az group create
```

Agar 4 Resource Groups banane hain:

```
Command 1 → First RG create
Command 2 → Second RG create
Command 3 → Third RG create
Command 4 → Fourth RG create
```

Yahan hum Azure ko commands ke through instructions de rahe hain.

Isliye ye **Imperative Automation** ka example hai.

---

# 8. Imperative Approach ko deeply samjho

Maan lo requirement hai:

> 4 Resource Groups create karo.

Imperative approach:

```
START

Create RG 1
Create RG 2
Create RG 3
Create RG 4

END
```

Yahan developer/operator ka control hota hai:

- Execution sequence
- Commands
- Logic
- Steps

### Important technical statement:

> In an **imperative model**, the engineer explicitly defines the sequence of operations required to reach the desired infrastructure state.

Ye sentence interview mein impact create karega.

---

# 9. Terraform aur Declarative Approach

Terraform mein hum commands ka detailed sequence generally define nahi karte ki:

```
First RG create karo
Then Storage Account create karo
Then VNet create karo
```

Instead hum infrastructure configuration likhte hain.

Example:

```
resource "azurerm_resource_group" "example" {
  name     = "rg-production"
  location = "Central India"
}
```

Yahan humne kya define kiya?

```
Desired Resource = Resource Group

Name = rg-production

Location = Central India
```

Terraform configuration ko read karta hai aur desired infrastructure create karne ke liye execution plan banata hai.

---

# 10. Terraform ka sabse important concept

Terraform mein generally hum bolte hain:

> **This is the desired state of my infrastructure.**

For example:

```
I want:

4 Resource Groups
1 VNet
3 Subnets
1 Storage Account
2 Virtual Machines
```

Terraform configuration read karega.

Current infrastructure aur desired infrastructure compare karega.

Uske baad required changes execute karega.

Yahan ek bahut important technical term hai:

# **Desired State**

Aur doosra:

# **Current State**

Terraform ka workflow in dono ke comparison ke around samjha ja sakta hai.

---

# 11. Declarative Infrastructure Example

Requirement:

> 4 Resource Groups create karne hain.

Terraform configuration conceptual form mein:

```
Resource Group 1
Resource Group 2
Resource Group 3
Resource Group 4
```

Tumne final infrastructure requirement declare kar di.

Terraform required resource creation operations handle karega.

### Interview language:

> Terraform follows a **declarative Infrastructure as Code approach**, where we define the desired state of infrastructure rather than manually specifying every execution step.

**Infrastructure as Code (IaC)** ek important technical keyword hai.

---

# 12. Azure CLI vs Terraform

Bahut important interview question:

> What is the difference between Azure CLI and Terraform?

## Azure CLI

Azure CLI:

- Command-line tool hai
- Azure resources manage karta hai
- Commands run karte hain
- Imperative automation commonly represent karta hai

Example mindset:

```
Do this
Then do this
Then create this
```

---

## Terraform

Terraform:

- **Infrastructure as Code tool**
- Infrastructure configuration files use karta hai
- Declarative model follow karta hai
- Multiple cloud providers support karta hai

Example mindset:

```
This is the infrastructure I want.
```

---

# 13. Visual Mental Model

```
                Infrastructure Creation
                         |
        -----------------------------------
        |                                 |
      Manual                         Automation
        |                                 |
   Azure Portal                ---------------------
                              |                   |
                         Imperative         Declarative
                              |                   |
                           Azure CLI           Terraform
```

---

# 14. Manual vs Automation

## Manual

```
Human
  ↓
Azure Portal
  ↓
Click and Configure
  ↓
Azure Resource
```

---

## Automation

```
Engineer
  ↓
Script / Configuration
  ↓
Automation Tool
  ↓
Azure API / Azure Platform
  ↓
Azure Resources
```

Production environment mein ye second approach zyada scalable hota hai.

---

# 15. Enterprise mein Manual Approach ki problems

Maan lo ek company ke paas:

```
Development Environment
Testing Environment
Staging Environment
Production Environment
```

Har environment mein similar infrastructure hai.

Example:

```
VNet
Subnets
NSG
Storage
VM
Key Vault
Monitoring
```

Agar sab manually create karoge:

### Problem 1: Human Error

Ek engineer:

```
Port 443 open
```

Doosra engineer:

```
Port 80 only
```

Configuration inconsistency ho gayi.

---

### Problem 2: Configuration Drift

Ye important interview keyword hai:

# **Configuration Drift**

Meaning:

Actual infrastructure aur expected/standard configuration ke beech difference aa jana.

Example:

Development:

```
NSG Rule A
```

Production:

```
NSG Rule B
```

Jabki ideally dono standard architecture follow karne chahiye.

---

### Problem 3: Repeatability Issue

Aaj manually infrastructure create kiya.

Kal same infrastructure dobara banana hai.

Phir manually same steps repeat karne padenge.

Automation/IaC mein:

```
Same Code
        ↓
Repeatable Infrastructure
```

Isko bol sakte hain:

# **Repeatability**

---

# 16. Enterprise mein Terraform kyu useful hai?

Terraform ke through infrastructure:

```
Code mein define
        ↓
Git Repository mein store
        ↓
Pull Request
        ↓
Code Review
        ↓
Validation
        ↓
Security Scan
        ↓
Plan
        ↓
Approval
        ↓
Apply
```

Ye enterprise-level workflow hai.

---

# 17. Production Terraform Workflow

A real production flow kuch is type ka ho sakta hai:

```
Developer
    ↓
Create Feature Branch
    ↓
Write Terraform Code
    ↓
terraform fmt
    ↓
terraform validate
    ↓
Security Scanning
    ↓
Terraform Plan
    ↓
Pull Request
    ↓
Code Review
    ↓
Merge to Main
    ↓
Approval
    ↓
terraform apply
    ↓
Azure Infrastructure
```

Yahan important interview words:

- **Version Control**
- **Pull Request**
- **Code Review**
- **Infrastructure Validation**
- **Security Scanning**
- **Change Management**
- **Deployment Pipeline**
- **Approval Gate**

---

# 18. Terraform ko directly production mein kyu nahi chalana chahiye?

Suppose developer ne directly:

```
terraform apply
```

Production subscription mein run kar diya.

Risk:

- Wrong resource deletion
- Wrong configuration
- Unexpected infrastructure changes
- Security misconfiguration
- Cost increase

Isliye enterprise best practice:

```
Code
 ↓
Review
 ↓
Validate
 ↓
Security Scan
 ↓
Plan
 ↓
Approval
 ↓
Apply
```

---

# 19. Important Terraform Best Practices

## 1. Infrastructure as Code

Infrastructure ko manually manage karne ke bajay code mein define karo.

---

## 2. Version Control

Terraform code ko **Git repository** mein store karo.

Benefits:

- History
- Collaboration
- Rollback understanding
- Code review

---

## 3. Remote State

Production mein local state file par depend karna generally suitable nahi hota.

Terraform state ko secure remote backend mein manage kiya ja sakta hai.

Azure environment mein commonly:

```
Azure Storage Account
        ↓
Blob Container
        ↓
Terraform State
```

Important keyword:

# **Remote State Management**

---

## 4. State Security

Terraform state mein sensitive information potentially ho sakti hai.

Isliye:

- Proper access control
- Secure storage
- Encryption
- Least privilege

important considerations hain.

---

## 5. Modular Architecture

Large Terraform project:

```
One huge file
```

mein nahi hona chahiye.

Better structure:

```
modules/
    resource-group/
    networking/
    storage/
    virtual-machine/

environments/
    dev/
    test/
    prod/
```

Is concept ko bolte hain:

# **Modular Infrastructure**

---

# 20. Prerequisites for Azure CLI Automation

Diagram mein kuch prerequisites highlight kiye gaye hain. diagram (12).pdfPDF

## Azure Cloud Access

Aapke paas Azure environment hona chahiye.

---

## Azure CLI Installed

Local system par Azure CLI installed hona chahiye.

Verification:

```
az version
```

---

## Authentication

Azure account ke through authentication required hoti hai.

Commonly:

```
az login
```

---

## Authorization

Sirf login karna enough nahi hai.

User ke paas required permissions honi chahiye.

Diagram mein specifically:

> **Contributor Rights on Subscription**

highlight kiya gaya hai. diagram (12).pdfPDF

---

# 21. Authentication vs Authorization

Ye bahut important interview topic hai.

## Authentication

Question:

> Who are you?

Example:

```
User logs into Azure.
```

---

## Authorization

Question:

> What are you allowed to do?

Example:

```
Can this user create a Resource Group?
```

Iske liye RBAC role required ho sakta hai.

---

# 22. Contributor Role kya hota hai?

Azure RBAC mein **Contributor** role generally resources manage/create karne ki permissions provide karta hai, lekin identity access management permissions ka scope alag hota hai.

Interview mein simply:

> **Authentication verifies identity, while authorization determines the actions that an authenticated identity is allowed to perform. Azure RBAC is used to manage those permissions.**

Ye professional answer hai.

---

# 23. Resource Group Creation ka Full Flow

## Manual Flow

```
Login to Azure Portal
        ↓
Select Subscription
        ↓
Go to Resource Groups
        ↓
Create
        ↓
Enter Resource Group Name
        ↓
Select Region
        ↓
Review
        ↓
Create
```

---

## Azure CLI Flow

```
Install Azure CLI
        ↓
Authenticate
        ↓
Select Subscription
        ↓
Run Azure CLI Command
        ↓
Azure API Request
        ↓
Resource Group Created
```

---

## Terraform Flow

```
Write Terraform Configuration
        ↓
terraform init
        ↓
terraform fmt
        ↓
terraform validate
        ↓
terraform plan
        ↓
Review Execution Plan
        ↓
terraform apply
        ↓
Azure Resources Created
```

---

# 24. Terraform ke Important Commands

## terraform init

Terraform project initialize karta hai.

Common activities include:

- Provider initialization
- Backend initialization
- Required modules download

Keyword:

# **Initialization**

---

## terraform fmt

Code formatting standardize karta hai.

Keyword:

# **Code Consistency**

---

## terraform validate

Configuration syntax and internal consistency validate karta hai.

Keyword:

# **Configuration Validation**

---

## terraform plan

Terraform batata hai:

```
Kya create hoga?
Kya modify hoga?
Kya destroy ho sakta hai?
```

Ye production workflow mein bahut important stage hai.

Keyword:

# **Execution Plan**

---

## terraform apply

Approved configuration ke according infrastructure changes execute karta hai.

Keyword:

# **Infrastructure Provisioning**

---

# 25. Azure Resource Group ko simple language mein samjho

Resource Group Azure resources ko logically organize karne ka ek container hai.

Example:

```
Resource Group: rg-production

Inside:

Virtual Network
Storage Account
Virtual Machine
Key Vault
Public IP
```

Logical grouping ka benefit:

- Management
- Access Control
- Monitoring
- Cost Management
- Lifecycle Management

---

# 26. Production Naming Convention

Production environment mein random names avoid karte hain.

Bad:

```
test123
rg123
newresource
```

Better:

```
rg-app-prod-centralindia
```

Naming convention:

```
<ResourceType>-<Application>-<Environment>-<Region>
```

Example:

```
rg-payments-prod-centralindia
```

Technical keyword:

# **Naming Standardization**

---

# 27. Environment Separation

Enterprise environment:

```
Development
     ↓
Testing
     ↓
Staging
     ↓
Production
```

Usually environments logically separate rakhe jaate hain according to organizational architecture.

Example:

```
dev
test
uat
prod
```

Terraform mein configuration/environment separation carefully design ki jati hai.

---

# 28. Tags ka use

Production resources par tags use kiye ja sakte hain.

Example:

```
Environment = Production
Application = Payment
Owner = DevOpsTeam
CostCenter = Finance
```

Benefits:

- Cost tracking
- Resource ownership
- Automation
- Reporting
- Governance

Keyword:

# **Resource Tagging Strategy**

---

# 29. Imperative vs Declarative — Real Production Thinking

## Imperative

Engineer bolta hai:

> "First ye command execute karo, then ye command execute karo."

---

## Declarative

Engineer bolta hai:

> "Ye meri required infrastructure configuration hai."

Tool state ko evaluate karke changes perform karta hai.

---

# 30. Important Enterprise Keywords

In words ko interview mein naturally use karo:

### **Infrastructure as Code (IaC)**

Infrastructure ko code/configuration files ke through manage karna.

---

### **Desired State**

Infrastructure ka expected final configuration.

---

### **State Management**

Infrastructure state ko track/manage karna.

---

### **Idempotency**

Ek desired operation ko repeat karne par unnecessary different result create na ho.

Terraform discussion mein carefully bol sakte ho:

> Terraform desired state ke basis par infrastructure changes manage karne ke liye state information use karta hai.

---

### **Configuration Drift**

Actual infrastructure expected configuration se differ karne lage.

---

### **Version Control**

Infrastructure code ko Git mein manage karna.

---

### **Repeatability**

Same code se consistent infrastructure create kar pana.

---

### **Consistency**

Different environments mein standardized configuration maintain karna.

---

### **Scalability**

Large number of resources ko efficiently manage kar pana.

---

### **Governance**

Policies, standards aur organizational controls maintain karna.

---

### **Least Privilege**

User/service identity ko sirf required permissions dena.

---

# 31. Technical Words ko use karke Interview Flow

Agar interviewer pooche:

> Why do we use Terraform instead of creating resources manually?

Aap aise flow mein answer doge:

### Step 1

Manual infrastructure management small environments ke liye possible hai.

### Step 2

Enterprise scale par manual provisioning problems create karta hai:

- Human error
- Inconsistency
- Configuration drift

### Step 3

Terraform provides:

- **Infrastructure as Code**
- **Repeatability**
- **Version Control**
- **Standardization**

### Step 4

Terraform declarative approach follow karta hai.

### Step 5

Hum desired infrastructure configuration define karte hain.

### Step 6

Production mein Terraform ko CI/CD workflow ke through:

```
Validate
Scan
Plan
Review
Approve
Apply
```

execute karna better practice hai.

---

# 32. English Answer to Speak in Interview

## Question: What is the difference between Imperative and Declarative Automation?

> "Imperative automation focuses on how to perform a task. In this approach, we explicitly define the sequence of steps or commands required to achieve the desired result. Azure CLI commands are a common example of an imperative approach.
> 
> Declarative automation focuses on what the desired final state should be. Instead of specifying every execution step, we define the required infrastructure configuration. Terraform follows a declarative Infrastructure as Code approach, where we define the desired state of resources and Terraform determines the necessary infrastructure changes.
> 
> In enterprise environments, declarative Infrastructure as Code provides better repeatability, consistency, version control, and scalability. It also helps reduce manual configuration errors and supports standardized deployment through CI/CD pipelines."

---

# 33. English Answer: Why Terraform Instead of Manual Creation?

> "Manual resource creation through the Azure Portal is useful for learning or small tasks, but it becomes difficult to manage at enterprise scale.
> 
> In a production environment, manual provisioning can lead to human errors, inconsistent configurations, and configuration drift across environments.
> 
> Terraform allows us to manage infrastructure using Infrastructure as Code. We can define the infrastructure in configuration files, store the code in version control, review changes through pull requests, validate the configuration, generate an execution plan, and deploy infrastructure through controlled CI/CD pipelines.
> 
> This provides repeatability, consistency, scalability, and better governance."

---

# 34. English Answer: Azure CLI vs Terraform

> "Azure CLI is primarily used to interact with Azure through commands and is commonly associated with an imperative approach, where we define the sequence of operations.
> 
> Terraform is an Infrastructure as Code tool that follows a declarative approach. With Terraform, we define the desired state of infrastructure in configuration files, and Terraform creates an execution plan to manage the required changes.
> 
> For enterprise infrastructure management, Terraform is particularly useful because it supports version-controlled, repeatable, and standardized infrastructure deployments."

---

# 35. Connected Topic Flow

Is topic ke baad naturally ye topics connect hote hain:

```
Manual Infrastructure
        ↓
Automation
        ↓
Imperative Approach
        ↓
Declarative Approach
        ↓
Azure CLI
        ↓
Terraform
        ↓
Infrastructure as Code
        ↓
Terraform Configuration
        ↓
Providers
        ↓
Resources
        ↓
Variables
        ↓
State File
        ↓
Remote Backend
        ↓
Modules
        ↓
Terraform Plan
        ↓
CI/CD Pipeline
        ↓
Security Scanning
        ↓
Production Deployment
        ↓
Azure Governance
```

---

# 36. Complete Interview End-to-End Flow

Ye overall flow yaad rakho:

## Level 1: Basic

```
What is Manual Infrastructure?
        ↓
What is Automation?
```

## Level 2: Automation Type

```
Imperative
        vs
Declarative
```

## Level 3: Tools

```
Azure CLI
        ↓
Imperative

Terraform
        ↓
Declarative
```

## Level 4: IaC

```
Terraform
        ↓
Infrastructure as Code
        ↓
Configuration Files
        ↓
Desired State
```

## Level 5: Production

```
Git
 ↓
Feature Branch
 ↓
Terraform Code
 ↓
fmt
 ↓
validate
 ↓
Security Scan
 ↓
plan
 ↓
Pull Request
 ↓
Code Review
 ↓
Approval
 ↓
apply
```

## Level 6: Enterprise

```
RBAC
 ↓
Least Privilege
 ↓
Remote State
 ↓
Modular Architecture
 ↓
Environment Separation
 ↓
Governance
 ↓
Monitoring
```

---

# 37. Short Powerful Answer — Interview Revision

> **"Manual infrastructure management is suitable for small or learning environments, but it is difficult to scale in production. Automation can be imperative or declarative. In an imperative approach, we specify how to perform each task, for example using Azure CLI commands. In a declarative approach, we define the desired state of the infrastructure, which is the approach used by Terraform. Terraform enables Infrastructure as Code, allowing us to maintain infrastructure in version control and deploy it in a repeatable, consistent, and scalable manner. In enterprise environments, Terraform deployments are typically integrated with CI/CD pipelines along with validation, security scanning, execution plans, code reviews, and approval processes."**

---

# 38. Is Topic ka Final Flow — Written to Speak

```
Manual Creation
      ↓
Azure Portal
      ↓
Problems at Enterprise Scale
      ↓
Automation
      ↓
Imperative Approach
      ↓
Azure CLI
      ↓
Declarative Approach
      ↓
Terraform
      ↓
Infrastructure as Code
      ↓
Desired State
      ↓
Terraform Plan
      ↓
Version Control
      ↓
CI/CD
      ↓
Validation
      ↓
Security Scanning
      ↓
Approval
      ↓
Production Deployment
      ↓
Consistent and Repeatable Infrastructure
```

### Sabse powerful technical sentence:

> **"The key difference is that imperative automation focuses on how to achieve the infrastructure state, whereas declarative Infrastructure as Code focuses on defining what the desired infrastructure state should be."**
