pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'D:\\\\gradle-6.0.1\\\\bin\\\\gradle build'
        bat 'D:\\gradle-6.0.1\\bin\\gradle javadoc'
        archiveArtifacts 'build\\libs\\*'
        archiveArtifacts 'build\\docs\\javadoc\\*'
        junit 'build\\test-results\\test\\*'
      }
    }

    stage('Mail') {
      steps {
        mail(subject: 'mail notification', to: 'gm_yousfi@esi.dz', body: 'lkjhgfdsftyuiop', replyTo: 'gm_yousfi@esi.dz')
      }
    }

    stage('code analysis') {
      parallel {
        stage('code analysis') {
          steps {
            withSonarQubeEnv('sonar') {
              bat 'D:\\gradle-6.0.1\\bin\\gradle sonarQube'
            }

            waitForQualityGate true
          }
        }

        stage('Test reporting ') {
          steps {
            jacoco()
          }
        }

      }
    }

    stage('jacoco') {
      steps {
        jacoco()
      }
    }

    stage('Deploiment') {
      steps {
        bat 'D:\\gradle-6.0.1\\bin\\gradle publish'
      }
    }

    stage('slack') {
      steps {
        slackSend(baseUrl: 'https://hooks.slack.com/services/', channel: 'general', message: 'blabla is sending!', token: 'TRRNQTS4X/BSWF21YG3/NEuc7ZqaQLRTtV9wiBmZNK1Z', teamDomain: 'yousfimeriem', color: 'danger')
      }
    }

  }
}