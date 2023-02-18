pipeline {
  agent any
  stages{
    stage ('Build'){
      steps{
        sh 'mvn clean install'
        echo 'Build Stage Successfull'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
        echo 'Test Stage Successfull'
        post{
          always{
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    post{
      failure{
        echo 'Pipeline failed'
      }
    }
  }
}
