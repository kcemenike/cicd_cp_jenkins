# AWS DevOps at (almost) no cost with GitHub, CodePipeline, Docker and Jenkins — a microservice-deployment

You can effectively deploy a CI/CD pipeline without having to break the bank, with a combination of the right tools.

Here’s how I pulled it off, with a combination of GitHub (for repository management), Jenkins (build management) CodePipeline (deployment management) and S3.

For this example, I intend to deploy a simple react app, so I set up a repository on Github, and an S3 bucket to hold my website files. You can choose your mode of deployment based on your use case (EC2, DynamoDB, Lambda, etc).

Create a brand-new repo (or you can fork this then clone to your local computer)

```sh
#!/bin/bash
# cicd_cp_jenkins directory
git init
git remote add origin https://github.com/kcemenike/cicd_cp_jenkins
git pull --set-upstream origin main
rm -rf frontend
npm init react-app frontend .

cd frontend
rm -rf .git
npm install
npm run build
git add .
git commit -m "frontend init"
git push -u origin main
```
View the rest of the instructions to set up AWS CodePipeline and Jenkins integration here:
https://medium.com/@kcemenike/aws-devops-at-almost-no-cost-with-github-codepipeline-docker-and-jenkins-a-97d96c6746f0
