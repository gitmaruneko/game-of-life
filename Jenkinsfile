pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('clean') {
      steps {
        build 'mvn clean'
      }
    }
    stage('test') {
      steps {
        build 'mvn package'
      }
    }
    stage('end') {
      steps {
        mail(subject: 'Jenkins Build', body: 'test 0118', to: 'hhuang10@lenovo.com')
      }
    }
  }
}