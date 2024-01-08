pipeline {
     agent { label 'Jenkins-Agent' }
    tools {
         jdk 'Java17'
         maven 'Maven3'
          }
    stages {
         stage ("cleanup workspace"){
                 steps {  
                 cleanWs()
             }
            } 
         stage( "checkoutfrom SCM "){
                 steps{
                  gir branch: 'main', credentialsId: 'github', url: 'https://github.com/Jagadishdevopstraining/maven-web-application.git'
                   }
            }
         stage("Build applictions"){
                 steps{
                     sh "mvn clean package"
               }
          
            }
          stage ("Test application"){
                  steps {
                      sh "mvn test"
              }
         }
        
   }
}
