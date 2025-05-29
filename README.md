Project Title :
**CI/CD Pipeline for Node.js App using Jenkins, Docker & Kubernetes .**
Description : "Set up a real-time CI/CD pipeline where Jenkins auto-builds a Docker image on GitHub commit, pushes it to Docker Hub, and deploys it to a Kubernetes cluster on AWS EC2. Used Declarative Jenkinsfile, Kubernetes YAML, and Docker for full automation." 


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
         - GitHub: Source code repository.
         - Jenkins: CI/CD automation tool.
         - Node.js: Application runtime.
         - Docker: Containerization.
         - Docker Hub: Image registry.
         - Kubernetes: Container orchestration.

________________________________________________________________
**Steps :**
1. create 2 mediaum instance and connect putty.
2. connect node > master 
3. install docker.io in master
4. enter command :
  docker run -u 0 --privileged --name jenkins -it -d -p 8080:8080 -p 50000:50000 -v
/var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -v /home/jenkins_home:/var/jenkins_home jenkins/jenkins:latest

   Check : docker ps -a
           kubectl get nodes 

6. login jenkins in browser
7. add (2)credential and plugin 
8. new item --> create pipeline --> add pipeline and build
9. after run website in browser (publicip : 31110 )
_______________________________________________________________________________________________________________

Add External plugin : in jenkins -> Advanced Plugin -> choose file : kubernetes-cd.hpi 
Available Plugin : docker pipeline, pipeline stage view

_________________________________________________________________

**Add Credential** : Docker hub id and password , Describe : dockerlogin
select kubernetes : id -> kubernets 

after click on enter : 
open master putty : cat ~/.kube/config
select all ( api version to last line ) copy paste in jenkins kubernets .
_________________________________________________________________

Add Pipeline in jenkins 
buid project 
_____________________________________________
output : ![Screenshot 2025-05-27 224122](https://github.com/user-attachments/assets/6610efe0-0ac0-4acf-9516-c3946b9b5d4c)

if any changes in index.html or yml file 
after enter this command
'''
kubectl delete all --all
'''
after build pipeline and run project
