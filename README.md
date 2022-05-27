# MavenHelloWorld

![Jenkins](https://img.shields.io/jenkins/build?jobUrl=http%3A%2F%2F13.126.235.47%3A8080%2Fjob%2FMavenHelloWorld%2F)

This project exists for the purpose of testing Jenkins CI/CD Server. It is a minimal Maven project with test. To use it, simply create a pipeline in Jenkins and add the url. Maven needs to be installed in order for this to work. I am planning to add tools in Jenkinsfile to streamline the process however I thought it would be better to have it preconfigured as not all tools can be automatically installed by Jenkins. 

Post building it sends the status of the build to hardcoded email id. PRs to make it more dynamic and send it to the build requestor are welcome. 
