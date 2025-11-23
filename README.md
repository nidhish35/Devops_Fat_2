DevOps Assignment – Dockerfile + Basic Linux Commands
 1. Five DevOps Concepts
1. CI/CD (Continuous Integration and Continuous Deployment)
A development practice where code changes are automatically built, tested, and deployed so that software updates reach production quickly and safely.
2. Infrastructure as Code (IaC)
Managing and provisioning infrastructure through code instead of manual configuration. Tools like Terraform and Ansible help automate servers, networks, and environments.
3. Containerization
Packaging applications and their dependencies inside lightweight, portable containers. Docker helps ensure consistency across development, testing, and production.
4. Version Control (Git)
A system used to track project changes, collaborate with others, manage branches, and maintain the entire development history.
5. Automation
Reducing manual activities—like testing, building, and deployments—by using scripts, pipelines, and tools to increase speed and avoid human errors.
 2. How I Completed This Assignment
Step 1: Created the Dockerfile
I created a Dockerfile using Ubuntu as the base image.
Inside it, I installed basic Linux utilities and copied a shell script that runs some Linux commands.
Example Dockerfile:
FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    tree \
    procps \
    && apt-get clean

COPY commands.sh /commands.sh
RUN chmod +x /commands.sh

CMD ["/bin/bash", "/commands.sh"]
Step 2: Created commands.sh
This script contains basic Linux commands such as:
#!/bin/bash
echo "Current Directory:"
pwd

echo "Listing Files:"
ls -l

echo "Disk Usage:"
df -h

echo "Running Processes:"
ps aux

echo "Directory Tree:"
tree /
Step 3: Built the Docker Image
Commands used:
docker build -t my-linux-commands .
Step 4: Ran the Docker Container
docker run -it my-linux-commands
Step 5: Initialized Git Repository
git init
git add .
git commit -m "Initial commit with Dockerfile and commands.sh"
Step 6: Connected to GitHub Repo
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
📌 3. How This Assignment Helps Me Learn DevOps, Linux, Git & Docker
🟦 DevOps
This assignment introduces practical DevOps concepts like automation, containerization, and working with infrastructure in a reproducible way.
🟩 Linux
Creating and running Linux commands inside Docker helps me understand shell scripting, the Linux filesystem, and process management.
🟧 Git
Using Git to upload my project teaches version control basics—add, commit, push, branches, and connecting remote repositories.
🟦 Docker
Building images, writing Dockerfiles, and running containers teaches how applications can be packaged and run consistently across environments.
