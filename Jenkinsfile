
pipeline {
    agent { label 'slave_node' }

      stages {
         stage ('Build && push'){
             steps {
                 script{
               checkout scm

                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {

                 def customImage = docker.build("maniengg/jenkins4evaljnlpslave").withRun('-p 8087:8087')
                  

                 customImage.push()
                 customImage.pull()    
                 }
              }
            }
         }
     }
}

