
---

## 🔧 What I Did:

1. Created a basic Python app (`app.py`) that prints a message.
2. Wrote a `Dockerfile` to containerize the app.
3. Created a `Jenkinsfile` to:
   - Build the Docker image
   - Run the container
4. Pushed the entire code to GitHub.
5. Configured Jenkins to pull the code and run the pipeline automatically.

---

## 🐳 Docker Usage:

- **Dockerfile** creates a Python-based container.
- Jenkins pipeline builds and runs the container during CI/CD.

---

## 🔁 Jenkins Pipeline Stages:

1. **Build Docker Image:**  
   Builds a Docker image from the `Dockerfile`.

2. **Run Docker Container:**  
   Runs the container to execute `app.py`.

---

## 🚀 How to Run Jenkins with Docker:

```bash
docker run -d --name jenkins -p 8080:8080 -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  jenkins/jenkins:lts
