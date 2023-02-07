@Library('reactJS') _
pipeline {
   agent any
   stages {
      stage('Install') {
         steps {
            sh 'yarn start'
         }
      }
     stage('Test') {
         steps {
            sh 'yarn test'
         }
      }
      stage('Build') {
         steps {
            sh 'yarn build'
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
