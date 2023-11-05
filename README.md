# sample-jenkins-node.js-docker-project-05-11-2023
sample-jenkins-node.js-docker-project-05-11-2023

This project is for deploying a simple HTML project by using nginx base image and docker and automating with Jenkins 
for all We can use EC2 machines. I tried with Ubuntu Jenkins server by installing Jenkins on it and editing proper security groups

STEPS:

1. get sample code from a free CSS website
2. create a separate directory for the particular project
3. Clone the GitHub repo (using SSH URL)
```
git clone .....
```
4. do your changes as per the below steps,

```
Clone the repo from another GitHub repo to some folder and then paste to the empty folder project05 

cd project05 

ll -ltr 

git init 

git status 

git add . 

git commit -m "adding all file" 

git checkout -b main 

git remote add sample-jenkins-node.js-docker-project-05-11-2023 git@github.com:hkalsait/sample-jenkins-node.js-docker-project-05-11-2023.git 

git pull sample-jenkins-node.js-docker-project-05-11-20231 main 

git push --set-upstream sample-jenkins-node.js-docker-project-05-11-20231 main 

git push -f --set-upstream sample-jenkins-node.js-docker-project-05-11-20231 main 
```

5. In the Jenkins server
download plugins for SSH, Docker and othe dependent...
add SCM -- github repo
crete the wehook in github  jenkins server ip/github-webhook/
choose your branch main/master

7. try to check the connection if jenkins build successfully or not?
8. Go to the Jenkins server and create user and gruop for docker and jenkins
```
sudo usermod -aG docker $USER
newgrp docker

-- Add the both users like 'jenkins' and 'Ec2-user or ubuntu' in docker group
8. If all success the added docker commands in build steps for automation 
```
docker stop my-nginx-container
docker rm --force my-nginx-container
docker rmi --force my-nginx 
docker build -t my-nginx .
docker run -d -p 8181:80 --name my-nginx-container my-nginx
```
Check the deployed application on jenkins port 8181
http://jenkins server ip:8181
