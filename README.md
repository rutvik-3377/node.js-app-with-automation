Project Title : **CI/CD Pipeline for Node.js App using Jenkins, Docker & Kubernetes .**
"Set up a real-time CI/CD pipeline where Jenkins auto-builds a Docker image on GitHub commit, pushes it to Docker Hub, and deploys it to a Kubernetes cluster on AWS EC2. Used Declarative Jenkinsfile, Kubernetes YAML, and Docker for full automation." 


🔄 DevOps CI/CD Workflow (Node.js App)
1. Developer commits code
  👨‍💻 → GitHub
       A developer writes code (Node.js in this case) and pushes it to a GitHub repository.
2. Jenkins triggers CI
   GitHub → Jenkins
      Jenkins checks out the latest code from GitHub when a commit is made.
      This initiates **Continuous Integration** (CI).
3. Run Tests
   Jenkins → Node.js Environment
      Jenkins uses a Node.js environment (or Docker-based Jenkins slave) to run automated tests.
4. Build Docker Image
  Jenkins → Docker Jenkins Slave
      Jenkins builds a Docker image of the application using the code and dependencies.
5. Push to Docker Hub
  Jenkins → Docker Hub
      The built Docker image is pushed to Docker Hub for image storage and sharing.
6. Deploy to Kubernetes
   Docker Hub → Kubernetes Cluster
      Kubernetes pulls the Docker image from Docker Hub.
      The image is then deployed across nodes in a Kubernetes cluster (Node1, Node2, etc.).


📌 Technologies Involved:
          GitHub: Source code repository
          Jenkins: CI/CD automation tool
          Node.js: Application runtime
          Docker: Containerization
          Docker Hub: Image registry
          Kubernetes: Container orchestration
