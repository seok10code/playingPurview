# Purview Integration Guide

This repository explains how to use **Microsoft Purview** for metadata management.

## 📌 Project Overview

My client needed a way to efficiently maintain metadata, enabling **easy data discovery** and **lineage tracking**. Their environment consisted of two source systems:

- **Databricks Unity Catalog**  
- **Meta Miner** (with an MSSQL backend)  

To integrate these systems, I connected **Databricks compute** and **MSSQL (Meta Miner’s backend)**.  
For authentication, I used **Azure Key Vault** to securely manage credentials.

## 🔗 Handling Meta Miner Metadata

Since **Meta Miner does not provide an API** for metadata retrieval, I extracted metadata as a **CSV file** and uploaded it to **Azure Data Lake Storage Gen2** using an API.  

To ensure **periodic metadata ingestion**, I automated this process using **Azure Data Factory**.

---

### ⚙️ Tech Stack

- **Microsoft Purview** – Metadata management  
- **Azure Key Vault** – Secure authentication  
- **Azure Data Lake Storage Gen2** – Metadata storage  
- **Azure Data Factory** – Automated data ingestion  

### 📂 File Structure

```plaintext
├── README.md
├── src/
│   ├── ingest_metadata.py   # Script to extract and upload metadata
│   ├── config.yaml          # Configuration settings
│   ├── utils.py             # Utility functions
└── docs/
    ├── architecture.png      # System architecture diagram
    └── process_flow.md       # Detailed process documentation
