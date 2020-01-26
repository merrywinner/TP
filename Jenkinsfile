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
        mail(subject: 'mail notification', to: 'gm_yousfi@esi.dz', body: '%Mlkjhytrezertyukilompù^')
      }
    }

  }
}