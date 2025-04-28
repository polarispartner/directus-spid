# ⚠️ Notice: Fork with SPID Authentication

> This repository is a **custom fork** of [Directus](https://directus.io) adapted to support **SPID Authentication** (Italian Public Digital Identity System).

Please note that it follows the official Directus releases but introduces customizations specific to SPID integration.  
If you are looking for the standard Directus project, visit the [official repository](https://github.com/directus/directus).

---

# 🛠️ How to Contribute to This Fork

Follow the steps below if you need to make changes or add features:

1. From the **GitHub "Tags"** section, **start from the latest `v11.6.1-spid<x>` version**.
2. Create a new branch (optional but recommended) and apply your changes.
3. Commit your changes normally.
4. Tag your commit using:
   
   ```bash
   git tag -a v11.6.1-spid<x> -m "Your commit message"
   ```

   Replace `<x>` with the next available subversion number (e.g., `v11.6.1-spid14`).

5. Push both commits and tags to the repository:

   ```bash
   git push origin --tags
   ```

---

# 📦 How to Build and Push the Docker Image to Azure ECR

After making changes, you can build and push a new Docker image following these steps:

1. **Login to Azure**:

   ```bash
   az login
   ```

2. **Build the Docker image**:

   ```bash
   docker build -t $IMAGE_NAME:$IMAGE_TAG .
   ```

   Example:

   ```bash
   docker build -t directus-spid:11.6.1-spid13 .
   ```

3. **Tag the Docker image for the Azure Container Registry**:

   ```bash
   docker tag $IMAGE_NAME:$IMAGE_TAG $LOGIN_SERVER/$IMAGE_NAME:$IMAGE_TAG
   ```

   Example:

   ```bash
   docker tag directus-spid:11.6.1-spid13 ifodevregistry.azurecr.io/directus-spid:11.6.1-spid13
   ```

4. **Push the Docker image to Azure ECR**:

   ```bash
   docker push ifodevregistry.azurecr.io/directus-spid:11.6.1-spid13
   ```

5. **If the push fails**, login to the Azure ECR with Docker:

   ```bash
   docker login $LOGIN_SERVER \
     --username <clientId> \
     --password <clientSecret>
   ```

   You can find the username and password in the Azure portal under:  
   **Settings → Identity** for your Azure Container Registry.

---
---

<p align="center"><img alt="Directus Logo" src="https://user-images.githubusercontent.com/522079/158864859-0fbeae62-9d7a-4619-b35e-f8fa5f68e0c8.png"></p>

---

## 🐰 Introduction

Directus is a real-time API and App dashboard for managing SQL database content.

- **REST & GraphQL API.** Instantly layers a blazingly fast Node.js API on top of any SQL database.
- **Manage Pure SQL.** Works with new or existing SQL databases, no migration required.
- **Choose your Database.** Supports PostgreSQL, MySQL, SQLite, OracleDB, CockroachDB, MariaDB, and MS-SQL.
- **On-Prem or Cloud.** Run locally, install on-premises, or use our
  [self-service Cloud service](https://directus.io/pricing).
- **Completely Extensible.** Built to white-label, it is easy to customize our modular platform.
- **A Modern Dashboard.** Our no-code Vue.js app is safe and intuitive for non-technical users, no training required.

**[Learn more about Directus](https://directus.io)** • **[Documentation](https://docs.directus.io)**

<br />

## 🚀 Directus Cloud

[Directus Cloud](https://directus.io/pricing) allows you to create projects, hosted by the Directus team, from
$15/month.

- A self-service dashboard to create and monitor all your projects in one place.
- Everything you need: Directus, database, storage, auto-scaling, and a global CDN.
- Select your desired region and provision a new project in ~90 seconds.

**[Create a Directus Cloud Project](https://directus.cloud)**

<br />

## 🤔 Community Help

[The Directus Documentation](https://docs.directus.io) is a great place to start, or explore these other channels:

- [Discord](https://directus.chat) (Questions, Live Discussions)
- [GitHub Issues](https://github.com/directus/directus/issues) (Report Bugs)
- [GitHub Discussions](https://github.com/directus/directus/discussions) (Feature Requests)
- [Twitter](https://twitter.com/directus) (Latest News)
- [YouTube](https://www.youtube.com/c/DirectusVideos/featured) (Video Tutorials)

<br />

## ❤️ Contributing & Sponsoring

Please read our [Contributing Guide](./contributing.md) before submitting Pull Requests.

All security vulnerabilities should be reported in accordance with our
[Security Policy](https://docs.directus.io/contributing/introduction/#reporting-security-vulnerabilities).

Directus is made possible with support from our passionate core team, talented contributors, and amazing
[GitHub Sponsors](https://github.com/sponsors/directus). Thank you all!

<br />

## 📄 Understanding Our License

Directus is licensed under [the Business Source License (BSL) 1.1](./license) with a permissive additional use grant.
For most users, it operates just like open source! Here's what that means for you:

### Free for Most Users

If your organization has less than $5M in annual revenue and/or funding combined, you can use Directus freely in any way
you'd like. Build that side project, launch your startup, or experiment with the platform — no strings attached.

### Enterprise Usage

For larger organizations (>$5M in annual revenue/funding) using Directus in production, we require a commercial license.
This model helps us maintain a sustainable balance: keeping Directus free for the majority of our community while
ensuring larger organizations who benefit from the platform contribute to its continued development.

### Why This Approach?

We believe in making powerful data tools accessible to everyone. This license lets us:

- Keep Directus free for individuals, startups, and smaller companies
- Maintain active development and strong support
- Continue improving the platform for everyone
- Stay sustainable as an independent project
