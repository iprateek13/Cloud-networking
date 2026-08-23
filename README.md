# ☁️ Azure & Networking — Cloud Knowledge Base

A practical and visual **Azure & Networking learning repository** built alongside hands-on practice.

This repository is not just a collection of commands or Terraform code.  
It is designed as a **personal Cloud/DevOps knowledge base** where every topic is documented with:

- 📚 Detailed technical notes
- 🧠 Simple explanations & analogies
- 🏗️ Architecture diagrams
- 🎨 Draw.io editable diagrams
- 🖼️ Azure Portal screenshots
- 💻 Azure CLI commands
- 🧩 Terraform configurations
- 🔐 Security & best practices
- 🏭 Production / enterprise use cases
- 🎯 Interview-ready explanations

The notes are written in **Obsidian-compatible Markdown**, so the same knowledge base can be used locally in Obsidian and version-controlled through Git/GitHub.

---

# 🎯 Purpose

The goal of this repository is to learn Azure and Networking in a way that goes beyond memorizing services.

For every topic, the focus is:

```text
What?
  ↓
Why?
  ↓
How?
  ↓
Where?
  ↓
When?
  ↓
Architecture
  ↓
Hands-on
  ↓
Security
  ↓
Production
  ↓
Troubleshooting
  ↓
Interview
```

The objective is to build the ability to **understand, implement, explain, troubleshoot, and design Azure infrastructure**.

---

# 🧠 Learning Philosophy

Instead of studying a service only from documentation, each topic is approached from multiple perspectives.

### Example: Azure VM

```text
Azure VM
   │
   ├── What is a VM?
   │
   ├── Why do we need it?
   │
   ├── How does it work?
   │
   ├── VM Architecture
   │
   ├── VNet
   │
   ├── Subnet
   │
   ├── NIC
   │
   ├── NSG
   │
   ├── Disks
   │
   ├── Azure CLI
   │
   ├── Terraform
   │
   ├── Security
   │
   ├── Production Architecture
   │
   └── Interview Explanation
```

This approach helps connect individual Azure services into a complete architecture.

---

# 📂 Repository Structure

```text
azure-networking/
│
├── README.md
│
├── Azure/
│   │
│   ├── Azure-Fundamentals/
│   │   ├── Azure-Overview.md
│   │   ├── Azure-Architecture.md
│   │   ├── Azure-Regions.md
│   │   ├── Availability-Zones.md
│   │   ├── Resource-Hierarchy.md
│   │   └── Microsoft-Entra-ID.md
│   │
│   ├── Compute/
│   │   ├── Azure-VM/
│   │   │   ├── Azure-VM.md
│   │   │   ├── architecture.drawio
│   │   │   ├── architecture.png
│   │   │   └── screenshots/
│   │   │
│   │   ├── VMSS/
│   │   └── Availability-Sets/
│   │
│   ├── Storage/
│   │   ├── Storage-Account/
│   │   ├── Blob-Storage/
│   │   └── Storage-Redundancy/
│   │
│   └── Identity-Security/
│       ├── RBAC/
│       ├── Managed-Identity/
│       └── Azure-Policy/
│
├── Networking/
│   │
│   ├── VNet/
│   ├── Subnet/
│   ├── IP-Addressing/
│   ├── NSG/
│   ├── Route-Table/
│   ├── NAT-Gateway/
│   ├── Load-Balancer/
│   ├── Application-Gateway/
│   ├── Azure-Bastion/
│   ├── Azure-Firewall/
│   ├── VNet-Peering/
│   ├── Private-Endpoint/
│   ├── Private-DNS/
│   ├── VPN-Gateway/
│   └── ExpressRoute/
│
├── Architectures/
│   ├── Three-Tier-Architecture/
│   ├── Hub-and-Spoke/
│   ├── Secure-Web-Application/
│   └── Enterprise-Network/
│
├── Azure-CLI/
│   ├── Compute/
│   ├── Networking/
│   ├── Storage/
│   └── Identity/
│
├── Terraform/
│   ├── Basics/
│   ├── Variables/
│   ├── Modules/
│   ├── Azure-Resources/
│   └── Azure-Networking/
│
└── Images/
    ├── Azure-Architecture/
    ├── Networking/
    └── Screenshots/
```

---

# 📝 Notes Format

All theoretical notes are primarily written in:

```text
.md
```

Markdown is used because it works naturally with **Obsidian and GitHub**.

A typical topic contains:

```text
Topic/
│
├── Topic.md
├── architecture.drawio
├── architecture.png
└── screenshots/
```

### File responsibilities

| File | Purpose |
|---|---|
| `.md` | Complete technical notes |
| `.drawio` | Editable architecture diagram |
| `.png` | Exported diagram for quick viewing |
| `.png/.jpg` screenshots | Azure Portal / practical evidence |
| `.tf` | Terraform implementation |
| `.yaml` | CI/CD configuration |

---

# 🧩 Standard Topic Template

Every major Azure/Networking topic follows a common structure.

```text
1. What is it?
2. Why do we need it?
3. Real-world analogy
4. Core components
5. How it works
6. Architecture
7. Networking flow
8. Azure Portal
9. Azure CLI
10. Terraform
11. Security
12. Production use cases
13. Best practices
14. Common mistakes
15. Troubleshooting
16. Interview explanation
17. Related Azure services
```

This creates consistency across the entire knowledge base.

---

# 🎨 Architecture & Draw.io

Architecture is an important part of this repository.

Instead of explaining infrastructure only through text, important architectures are represented visually.

Example:

```text
                    Internet
                       │
                       ▼
               Application Gateway
                       │
                       ▼
                  Web Subnet
                       │
                ┌──────┴──────┐
                ▼             ▼
              VM-1           VM-2
                │             │
                └──────┬──────┘
                       ▼
                Application Tier
                       │
                       ▼
                 Private Endpoint
                       │
                       ▼
                  Azure Database
```

The architecture is maintained as:

```text
architecture.drawio
```

and exported as:

```text
architecture.png
```

The `.drawio` file remains editable for future architecture changes.

---

# 🖼️ Screenshots & Visual Notes

Hands-on learning is documented with screenshots wherever useful.

For example:

```text
Azure-VM/
│
├── Azure-VM.md
├── architecture.drawio
├── architecture.png
│
└── screenshots/
    ├── 01-create-vm.png
    ├── 02-vm-overview.png
    ├── 03-networking.png
    ├── 04-nsg.png
    └── 05-disks.png
```

The Markdown notes reference these images:

```markdown
![VM Overview](screenshots/02-vm-overview.png)
```

This allows the same notes to remain visually useful inside Obsidian.

---

# 🔗 Obsidian Knowledge Graph

The repository uses Obsidian-style internal links to connect related concepts.

Example:

```markdown
Azure VM uses [[Virtual Network]].

The VM is deployed inside a [[Subnet]].

Traffic is controlled using [[Network Security Group]].

Secure administration can be performed using [[Azure Bastion]].

PaaS services can be accessed privately using [[Private Endpoint]].
```

This creates a connected knowledge graph instead of isolated notes.

Example:

```text
                 Azure VM
                    │
       ┌────────────┼────────────┐
       ▼            ▼            ▼
     VNet          NIC          Disk
       │
     Subnet
       │
      NSG
       │
    Bastion
```

---

# ☁️ Azure Topics

The repository progressively covers:

### Azure Fundamentals

- Azure Cloud
- Regions
- Availability Zones
- Region Pairs
- Subscriptions
- Resource Groups
- Management Groups
- Azure Resource Manager
- Microsoft Entra ID
- Azure Portal
- Azure CLI

### Compute

- Virtual Machines
- VM Scale Sets
- Availability Sets
- VM Sizes
- Managed Disks
- Images
- SSH
- Bastion

### Storage

- Storage Accounts
- Blob Storage
- Containers
- Storage Tiers
- Replication
- LRS
- ZRS
- GRS
- GZRS
- Lifecycle Management
- Private Access

### Identity & Security

- RBAC
- Managed Identity
- Azure Policy
- Resource Locks
- Key Vault
- Defender for Cloud
- Zero Trust
- Least Privilege

---

# 🌐 Networking Topics

### Fundamentals

- OSI Model
- TCP/IP
- IP Addressing
- CIDR
- Public vs Private IP
- DNS
- Ports
- Protocols
- Routing

### Azure Networking

- VNet
- Subnets
- NSG
- Route Tables
- UDR
- Public IP
- NIC
- NAT Gateway
- Load Balancer
- Application Gateway
- Azure Firewall
- Azure Bastion
- VNet Peering
- Private Endpoint
- Private DNS
- VPN Gateway
- ExpressRoute
- Network Watcher

### Enterprise Architecture

- Hub-and-Spoke
- Landing Zones
- Centralized Network Security
- Shared Services
- Network Segmentation
- Hybrid Connectivity
- Multi-VNet Architecture

---

# 💻 Azure CLI

Azure CLI commands are maintained alongside the concepts they manage.

Example:

```bash
az login
```

```bash
az group create \
  --name my-rg \
  --location centralindia
```

```bash
az vm create \
  --resource-group my-rg \
  --name my
