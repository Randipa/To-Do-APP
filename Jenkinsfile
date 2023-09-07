pipeline {
  agent any
  stages {
    stage('Log Tool Version') {
      parallel {
        stage('Log Tool Version') {
          steps {
            sh '''mvn --version
git --version
java -version'''
          }
        }

        stage('check For POM') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build with maven') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Post build step') {
      steps {
        writeFile(file: 'status.txt', text: 'Welcome-LOIT')
      }
    }

  }
}