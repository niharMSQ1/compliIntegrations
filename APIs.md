# Asset Management Tools: Common APIs Overview

This document provides an overview of the common API functionalities across the following asset management tools:

- **InvGate Asset Management**
- **SolarWinds**
- **SysAid**
- **ManageEngine**
- **Asset Panda**
- **Flexera**
- **Snow Software**
- **ServiceNow**
- **BMC Helix**
- **Ivanti Neurons**

---

## Common API Functionalities

### 1. Asset Retrieval
Retrieve the list of all assets or specific asset details.

| **Tool**                 | **Endpoint**                           |
|--------------------------|-----------------------------------------|
| InvGate                  | `/api/assets`                          |
| SolarWinds               | `/api/v1/assets`                       |
| SysAid                   | `/rest/assets`                         |
| ManageEngine             | `/api/cmdb/assets`                     |
| Asset Panda              | `/api/assets`                          |
| Flexera                  | `/assets/v1`                           |
| Snow Software            | `/api/v1/assets`                       |
| ServiceNow               | `/now/table/alm_asset`                 |
| BMC Helix                | `/api/arsys/v1/entry/Asset`            |
| Ivanti Neurons           | `/api/asset`                           |

---

### 2. Create or Update Assets
Add new assets or modify existing asset information.

| **Tool**                 | **Endpoint**                           |
|--------------------------|-----------------------------------------|
| InvGate                  | `/api/assets` (POST/PUT)               |
| SolarWinds               | `/api/v1/assets` (POST/PUT)            |
| SysAid                   | `/rest/assets/{id}` (POST/PUT)         |
| ManageEngine             | `/api/cmdb/assets` (POST/PUT)          |
| Asset Panda              | `/api/assets` (POST/PUT)               |
| Flexera                  | `/assets/v1/{asset_id}` (POST/PUT)     |
| Snow Software            | `/api/v1/assets/{id}` (POST/PUT)       |
| ServiceNow               | `/now/table/alm_asset` (POST/PUT)      |
| BMC Helix                | `/api/arsys/v1/entry/Asset` (POST/PUT) |
| Ivanti Neurons           | `/api/asset/{id}` (POST/PUT)           |

---

### 3. Search Assets
Search for assets based on filters such as type, status, or custom fields.

| **Tool**                 | **Endpoint**                              |
|--------------------------|--------------------------------------------|
| InvGate                  | `/api/assets/search`                      |
| SolarWinds               | `/api/v1/assets?filter={filter_query}`     |
| SysAid                   | `/rest/assets?search={query}`             |
| ManageEngine             | `/api/cmdb/assets/search?query={query}`   |
| Asset Panda              | `/api/assets/search`                      |
| Flexera                  | `/assets/v1/search`                       |
| Snow Software            | `/api/v1/assets?filter={filter_query}`    |
| ServiceNow               | `/now/table/alm_asset?sysparm_query={}`   |
| BMC Helix                | `/api/arsys/v1/entry/Asset?query={query}` |
| Ivanti Neurons           | `/api/asset/search`                       |

---

### 4. Asset Relationships
Retrieve relationships between assets or assets and other entities (e.g., users, tickets).

| **Tool**                 | **Endpoint**                              |
|--------------------------|--------------------------------------------|
| InvGate                  | `/api/assets/{id}/relationships`          |
| SolarWinds               | `/api/v1/assets/{id}/relations`           |
| SysAid                   | `/rest/assets/{id}/relations`             |
| ManageEngine             | `/api/cmdb/assets/{id}/relations`         |
| Asset Panda              | `/api/assets/{id}/relations`              |
| Flexera                  | `/assets/v1/{id}/relations`               |
| Snow Software            | `/api/v1/assets/{id}/relationships`       |
| ServiceNow               | `/now/table/alm_asset_relation`           |
| BMC Helix                | `/api/arsys/v1/entry/Asset/relationships` |
| Ivanti Neurons           | `/api/asset/{id}/relations`               |

---

### 5. Asset Deletion
Remove assets from the system.

| **Tool**                 | **Endpoint**                     |
|--------------------------|-----------------------------------|
| InvGate                  | `/api/assets/{id}` (DELETE)      |
| SolarWinds               | `/api/v1/assets/{id}` (DELETE)   |
| SysAid                   | `/rest/assets/{id}` (DELETE)     |
| ManageEngine             | `/api/cmdb/assets/{id}` (DELETE) |
| Asset Panda              | `/api/assets/{id}` (DELETE)      |
| Flexera                  | `/assets/v1/{id}` (DELETE)       |
| Snow Software            | `/api/v1/assets/{id}` (DELETE)   |
| ServiceNow               | `/now/table/alm_asset/{sys_id}`  |
| BMC Helix                | `/api/arsys/v1/entry/Asset/{id}` |
| Ivanti Neurons           | `/api/asset/{id}` (DELETE)       |

---

### 6. Authentication
Most tools use one of the following authentication methods:
- API Key
- OAuth2
- Basic Auth

| **Tool**                 | **Authentication Method**      |
|--------------------------|---------------------------------|
| InvGate                  | API Key                        |
| SolarWinds               | OAuth2                         |
| SysAid                   | API Key or OAuth2              |
| ManageEngine             | API Key                        |
| Asset Panda              | API Key                        |
| Flexera                  | OAuth2                         |
| Snow Software            | API Key                        |
| ServiceNow               | Basic Auth / OAuth2            |
| BMC Helix                | OAuth2                         |
| Ivanti Neurons           | API Key                        |

---

## Example: Fetching Assets

### InvGate
```bash
curl -X GET "https://your-invgate-instance.com/api/assets" \
-H "Authorization: Bearer YOUR_API_KEY"
