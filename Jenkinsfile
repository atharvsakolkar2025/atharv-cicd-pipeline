pipeline {
 agent-1

 stages {
     stage('Fetch code') {
            steps {
               git branch: 'atom', url: 'https://github.com/hkhcoder/vprofile-project.git'
            }
     }
       stage('UNIT TEST') {
            steps{
                sh 'mvn test'
            }
        }
     stage('Build'){
         steps{
            sh 'mvn package'
         }
         post {
            success {
               echo 'Now Archiving it...'
               archiveArtifacts artifacts: '**/target/*.war'
            }
         }
     }     
 }
}
