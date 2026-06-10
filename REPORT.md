# CloudShop Report

**Names:* Che Nanga Joy*  
**Date:* 10th June 2026*  
**GitHub URL:*https://github.com/joy859/cloudshop.tp*

## Git history

Paste here:
66a0cd1 (HEAD -> main, origin/main, origin/HEAD) ci: add github actions pipeline
bb268af Added iles
daf0149 update: phase B answers
da2b4df update: phase A answers
e602f18 docs: phase C devops pipeline
8bfa9d8 docs: phase B2 multicloud
874e423 docs: phase A cloud weeks 1-2
ad4b133 chore: init cloudshop repository
```
git log --oneline
```

## Phase D — GitHub Actions (PaaS or IaaS?)

**Is GitHub Actions closer to PaaS or IaaS?**

GitHub Actions is closer to **Platform as a Service (PaaS)**. It provides a ready-to-use platform for running automated workflows and CI/CD pipelines. Users do not need to manage servers, operating systems, or infrastructure. GitHub handles the underlying resources and execution environment. Developers only need to define the workflow steps, making it similar to a managed platform service.


## Phase E — Dockerfile

Explain each line of your Dockerfile (especially why `requirements.txt` is copied before `app.py`).
You can write this in your report:

### Explanation of the Dockerfile

```dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY app.py .
EXPOSE 5000
CMD ["python", "app.py"]
```

1. **FROM python:3.10-slim**
   Uses the official Python 3.10 slim image as the base image for the container. The slim version is smaller and uses less storage.

2. **WORKDIR /app**
   Sets `/app` as the working directory inside the container. All subsequent commands will run from this directory.

3. **COPY requirements.txt .**
   Copies the `requirements.txt` file from the project folder into the container's working directory.

4. **RUN pip install --no-cache-dir -r requirements.txt**
   Installs all Python dependencies listed in `requirements.txt`. The `--no-cache-dir` option reduces the image size by not storing installation cache files.

5. **COPY app.py .**
   Copies the Flask application file (`app.py`) into the container.

6. **EXPOSE 5000**
   Documents that the application uses port 5000 and allows it to be mapped to a port on the host machine.

7. **CMD ["python", "app.py"]**
   Specifies the command that runs automatically when the container starts. It launches the Flask application.

### Why is `requirements.txt` copied before `app.py`?

`requirements.txt` is copied first to take advantage of Docker's layer caching. If only `app.py` changes, Docker can reuse the previously built layer where dependencies were installed and avoid reinstalling them. This makes image builds much faster. If `requirements.txt` changes, Docker knows that dependencies must be reinstalled and rebuilds that layer accordingly.

## Phase F — Take-home summary

1. Week 1:
I learned the fundamentals of cloud computing and identified the advantages of using public cloud services for CloudShop.

2. Week 2:
I studied cloud service models (IaaS, PaaS, and SaaS) and classified services such as AWS EC2, GitHub, Docker Hub, Gmail, and GitHub Actions.

3. Week 3:
I designed an AWS architecture for CloudShop and learned about virtual machines, networking, ports, and SSH access.

4. Week 4:
I compared cloud providers (AWS, Azure, and GCP) and matched equivalent services such as EC2, S3, Route 53, and CodeBuild.

5. Week 5:
I designed a DevOps pipeline showing how code moves from local development through GitHub Actions testing and Docker image creation.

6. Week 6:
I created a Flask API, managed the project with Git and GitHub, and automated testing and builds using GitHub Actions.

7. Week 7:
I containerized the Flask application using Docker, built a Docker image, and ran the application locally in a container.

**Automation:** what happens when you `git push`?

When I run git push, my local commits are uploaded from my computer to the remote GitHub repository. GitHub then updates the repository with the latest changes and automatically triggers the GitHub Actions workflow configured for the project. The workflow runs the tests and builds the Docker image to verify that the application works correctly.
**Without AWS:** what did you simulate instead?
Without using AWS, I simulated a cloud deployment environment by running the Flask application locally and containerizing it with Docker. I also used GitHub Actions to automate testing and building, which allowed me to practice cloud and DevOps concepts without creating an actual AWS virtual machine.
## AWS bonus (optional)

(If applicable: IP, screenshots, instance termination date)
