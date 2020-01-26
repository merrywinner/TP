pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'D:\\\\gradle-6.0.1\\\\bin\\\\gradle build'
        bat 'D:\\gradle-6.0.1\\bin\\gradle javadoc'
        archiveArtifacts 'build\\C:\\Windows\\ServiceProfiles\\LocalService\\.jenkins\\workspace\\TP_master\\build\\libs\\*'
      }
    }

  }
}