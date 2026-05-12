# Module 5 Assignment: GitHub Actions Fundamentals

## 🎯 Project Overview
This repository contains the automated Continuous Integration (CI) pipeline for a React application. The pipeline is built using **GitHub Actions** and is configured to execute exclusively on the `development` branch using a custom **AWS EC2 Self-Hosted Runner**.

---

## 📋 Submission Checklist

- [x] **GitHub Repository Link:** https://github.com/khalid32/weather-app/tree/development
- [x] **Workflow YAML File:** Configured in `.github/workflows/ci-pipeline.yml`
- [x] **Successful Execution:** Screenshot attached below.
      <img width="1853" height="722" alt="Screenshot 2026-05-13 031126" src="https://github.com/user-attachments/assets/d8761fe0-ed1f-4388-b9c1-ec58826b3aa5" />
- [x] **Failed Pipeline Debugging:** Screenshot attached below.
      <img width="1843" height="799" alt="Screenshot 2026-05-13 014627" src="https://github.com/user-attachments/assets/75fdc072-14c9-406d-9c65-e22edfedbdac" />

- [x] **Short Written Explanations:** See the section below.

---

## 📝 Written Explanations

### 1. CI/CD (Continuous Integration / Continuous Deployment)
CI/CD acts as an "automated conveyor belt" for software development. **Continuous Integration (CI)** is the practice where developers frequently merge code changes into a central repository, which automatically triggers builds and tests to catch bugs early. **Continuous Deployment (CD)** takes over once the code passes testing, automatically deploying the application to a live server. The primary benefit of CI/CD is that it eliminates repetitive manual tasks, significantly speeds up the release cycle, and reduces the chance of human error during deployment.

### 2. Self-Hosted Runner
In GitHub Actions, a "Runner" is the machine or virtual environment that executes the automated jobs. While GitHub offers standard cloud-hosted runners, a **self-hosted runner** is a specific machine (like an AWS EC2 instance or a local computer) that you set up and manage yourself. The main advantage of using a self-hosted runner is that it gives you full control over the execution environment, allowing you to use custom hardware, specific installed tools, and internal network configurations that GitHub-hosted runners cannot access.

### 3. Workflow Execution Process
The GitHub Actions execution process follows a strict hierarchy: **Workflow → Job → Step → Runner**. The process begins with a specific event or *trigger* (such as a code push to the `development` branch). This trigger activates the *Workflow*. The workflow organizes tasks into *Jobs*, which are assigned to a specific *Runner* (in this case, your self-hosted machine). The runner then executes the individual *Steps* (which are shell commands or automated scripts) sequentially. As this happens, GitHub captures all standard output and standard errors in the *Workflow execution logs*, which serve as the primary source for debugging if the pipeline fails.
