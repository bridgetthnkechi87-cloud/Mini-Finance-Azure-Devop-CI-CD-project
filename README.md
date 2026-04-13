# Mini Finance – Azure DevOps CI/CD Project

## Overview
This project demonstrates a complete CI/CD pipeline using Azure DevOps to deploy a static finance web application to a Linux VM running NGINX.

The application is automatically deployed whenever changes are pushed to the `main` branch.

---

## Project Architecture

- **Source Code**: Azure Repos / GitHub
- **CI/CD Pipeline**: Azure DevOps YAML Pipeline
- **Deployment Target**: Ubuntu Linux VM
- **Web Server**: NGINX
- **Provisioning Tools**:
  - Terraform (Infrastructure)
  - Ansible (Configuration)

---

## Features

- Automated deployment on every commit to `main`
- Secure SSH connection to remote VM
- File transfer using Azure DevOps pipeline tasks
- NGINX setup and restart via pipeline
- Live web application accessible via public IP

---

## Pipeline Workflow

1. Trigger pipeline on push to `main`
2. Checkout repository
3. Copy project files to VM using SSH
4. Install/ensure NGINX is available
5. Deploy files to `/var/www/html`
6. Set permissions
7. Restart NGINX
8. Serve application on port 80

---

## Technologies Used

- Azure DevOps
- Azure Virtual Machine (Ubuntu)
- NGINX
- Terraform
- Ansible
- Git & GitHub

---

## Deployment

The application is accessible via:

Example (from this project):http://20.164.222.184


---

## Repository Structure
├── main.tf
├── variables.tf
├── outputs.tf
├── azure-pipelines.yml
├── index.html
├── css/
├── js/
└── images/


---

## Challenges & Solutions

- **Issue:** GitHub rejected large Terraform provider files  
  **Solution:** Removed `.terraform/` and state files using `.gitignore` and reinitialized Git history

- **Issue:** Authentication failure when pushing to GitHub  
  **Solution:** Switched from password to SSH authentication

- **Issue:** Pipeline not triggering  
  **Solution:** Corrected agent pool configuration and verified self-hosted agent status

---

## Author

**Ihuoma Nkechi Bridget**  
Cloud & DevOps Engineer  

---

## Status

✅ CI/CD Pipeline Working  
✅ Application Successfully Deployed  
✅ Live on VM via NGINX  

---

## Next Steps

- Add HTTPS (SSL with NGINX)
- Implement monitoring/logging
- Containerize application using Docker
