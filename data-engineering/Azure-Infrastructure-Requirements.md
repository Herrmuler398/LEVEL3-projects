# Azure Infrastructure Requirements

This document outlines the Azure infrastructure and services required for students to complete the Data Engineering track. The track is designed to simulate a real-world environment, requiring development and production setups.

## Core Services

### 1. Azure Subscription & Resource Group
- **Subscription**: An active Azure subscription.
- **Resource Groups**: At least one resource group (e.g., `rg-de-track-dev`), or two if separating dev and prod environments (`rg-de-track-prod`).

### 2. Azure Databricks (Premium Tier)
A **Premium** workspace is required to support Unity Catalog features like Row-Level Security, Column Masking, and SQL Warehouses.

- **Workspaces**:
  - One Development Workspace.
  - (Optional but Recommended for Part 6) One Production Workspace.
- **Compute**:
  - **All-Purpose Compute**: For interactive development (Notebooks).
  - **Job Compute**: For running scheduled workflows (Part 2 & 3).
  - **SQL Warehouse**: Required for Part 4 (Data Serving) and Part 7 (BI/Dashboards).
- **Unity Catalog**:
  - Must be enabled for the workspace(s).
  - Requires an **Access Connector for Azure Databricks** (Managed Identity).

### 3. Azure Data Lake Storage Gen2 (ADLS Gen2)
Primary storage for the Lakehouse architecture.

- **Storage Account**: Hierarchical Namespace enabled (ADLS Gen2).
- **Containers**:
  - `metastore-root`: (If managing own metastore) For Unity Catalog metadata.
  - `data`: To host the Unity Catalog Volumes and external tables.
    - Specific paths required: `/Volumes/track/incoming/...`

## DevOps & CI/CD (Part 6)

### 4. Azure DevOps
Required for "Taking to Production" and CI/CD pipelines.

- **Organization & Project**: An active project to host the repository and pipelines.
- **Azure Repos**: Git repository for version control of notebooks and code.
- **Azure Pipelines**: For defining YAML-based CI/CD pipelines.

## Security & Governance

### 5. Azure Key Vault
Required for secure credential management (Part 6).

- **Key Vault Resource**: To store:
  - OpenSky API Credentials.
  - Lufthansa API Credentials.
  - Service Principal Secrets (for CI/CD).

### 6. Identities & Access Management (IAM)
- **Service Principals**:
  - For Azure DevOps Service Connections to deploy to Databricks.
- **Managed Identities**:
  - For the Unity Catalog Access Connector to access ADLS Gen2.

## BI & Visualization

### 7. Power BI
Required for "BI on Lakehouse" (Part 7).

- **Power BI Desktop** (free) or **Power BI Service** account.
- Must support connectivity to Azure Databricks SQL Warehouse.

## Summary Checklist

| Service | Feature/Sku | Purpose |
|---------|-------------|---------|
| **Azure Databricks** | Premium | Core Platform, Unity Catalog, SQL Warehouses |
| **ADLS Gen2** | Standard/LRS | Data Lake Storage (Bronze/Silver/Gold) |
| **Key Vault** | Standard | Secret Management |
| **Azure DevOps** | Basic Plan | source Control & CI/CD |
| **Power BI** | Pro/Desktop | BI Reporting |

## Cost Estimation (Approximate)

The track is estimated to take **4 to 5 weeks** to complete. Costs are primarily driven by **Compute uptime** (Databricks clusters).

**Estimated Total Per Student: $100 - $150 USD** (assuming careful resource management).

### Cost Breakdown Assumptions (Per Student)

1. **Azure Databricks Compute (Interactive)**
   - *Usage*: ~10 hours/week × 5 weeks = 50 hours.
   - *Config*: Single Node, Standard_DS3_v2 (or similar).
   - *Cost*: ~$1.00 - $1.50 per hour.
   - *Subtotal*: ~$75.00

2. **Azure Databricks Jobs & SQL Warehouse**
   - *Usage*: Scheduled jobs and SQL query analysis.
   - *Subtotal*: ~$20.00 - $40.00

3. **Storage & Networking**
   - ADLS Gen2, Key Vault transactions.
   - *Subtotal*: < $5.00

### ⚠️ Cost Saving Tips
- **Auto-Termination**: Set Databricks clusters to auto-terminate after **15-20 minutes** of inactivity.
- **Single Node Clusters**: Use "Single Node" mode for development to avoid paying for driver + worker nodes.
- **Spot Instances**: Data Engineering workloads are often fault-tolerant; use Spot instances for worker nodes if using multi-node clusters.
- **Clean Up**: Delete resources (or the entire Resource Group) if taking a long break between study sessions.

