
pipeline {
    agent { label 'slave_node' }

      stages {
         stage ('Build && push'){
             steps {
                 script{
               checkout scm

                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {

                 def customImage = docker.build("maniengg/jenkins4evaljnlpslave").withRun('-p 8083:8080','jenkins-slave') {
                   
                  // customImage.push()
                  //  customImage.pull()
                                  
                  }   
                }
              }
            }
         }
     }
}

