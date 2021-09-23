pipeline {
  agent {
    node {
      label 'maven'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/fromzx/devops-java-sample.git', branch: 'master')
      }
    }

    stage('unit test') {
      agent {
        docker {
          image 'maven'
        }

      }
      steps {
        sh 'mvn clean  -gs `pwd`/configuration/settings.xml test'
      }
    }

  }
}