# nodeapp
CI/CD Pipeline for Node.js App using Jenkins, Docker &amp; Kubernetes
🔄 DevOps CI/CD Workflow (Node.js App)
Developer commits code
👨‍💻 → GitHub
A developer writes code (Node.js in this case) and pushes it to a GitHub repository.
Jenkins triggers CI
GitHub → Jenkins
Jenkins checks out the latest code from GitHub when a commit is made.
This initiates Continuous Integration (CI).
Run Tests
Jenkins → Node.js Environment
Jenkins uses a Node.js environment (or Docker-based Jenkins slave) to run automated tests.
Build Docker Image
Jenkins → Docker Jenkins Slave
Jenkins builds a Docker image of the application using the code and dependencies.
Push to Docker Hub
Jenkins → Docker Hub
The built Docker image is pushed to Docker Hub for image storage and sharing.
Deploy to Kubernetes
Docker Hub → Kubernetes Cluster
Kubernetes pulls the Docker image from Docker Hub.
The image is then deployed across nodes in a Kubernetes cluster (Node1, Node2, etc.).
