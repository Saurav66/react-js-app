@Library('reactJS') _
pipeline {
   agent any
   stages {
      stage('Install') {
         steps {
            sh 'npm install'
         }
      }
      stage('Test') {
         steps {
            sh 'npm test'
         }
      }
      stage('Push') {
         steps {
            sh 'docker build -t react-hello-world .'
            withDockerRegistry(credentialsId: 'docker') {
               sh 'docker push react-hello-world'
            }
         }
      }
   }
}
