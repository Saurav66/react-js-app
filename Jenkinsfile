@Library('reactJS') _
pipeline {
   agent any
   stages {
      stage('Install') {
         steps {
            sh 'npm install'
         }
      }
      stage('Build') {
         steps {
            sh 'npm run build'
         }
      }
     stage('Test') {
         steps {
            sh 'npm run test'
         }
      }
      stage('Push') {
         steps {
            sh 'sudo docker build -t react-hello-world .'
            withDockerRegistry(credentialsId: 'docker') {
               sh 'sudo docker push react-hello-world'
            }
         }
      }
   }
}
