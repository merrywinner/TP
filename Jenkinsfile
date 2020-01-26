pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'D:\\\\gradle-6.0.1\\\\bin\\\\gradle build'
        bat 'D:\\gradle-6.0.1\\bin\\gradle javadoc'
        archiveArtifacts 'build\\libs\\*'
        archiveArtifacts 'build\\docs\\javadoc\\*'
      }
    }

    stage('Mail') {
      steps {
        mail(subject: 'mail notification', to: 'merry.nonim@gmail.com', body: 'lkjhgfdsftyuiop')
      }
    }

  }
}