pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('maven') {
      parallel {
        stage('maven') {
          steps {
            withMaven(jdk: '1.8.0_151', maven: '3.5.2', mavenOpts: 'clean')
          }
        }
        stage('package') {
          steps {
            withMaven(jdk: '1.8_151', mavenOpts: 'clean', maven: '3.5.2') {
              withMaven(mavenOpts: 'package')
            }
            
          }
        }
      }
    }
    stage('Junit') {
      steps {
        junit '**/target/surefire-reports/*.xml'
      }
    }
    stage('end') {
      steps {
        mail(subject: 'Jenkins Build', body: 'test 0118', to: 'hhuang10@lenovo.com')
      }
    }
  }
}