pipeline {
  agent any
  stages {
    stage('SettingParm') {
      steps {
        bat 'echo \'hello\''
        input(message: 'Provide an build number', id: 'buildnr01', ok: 'Thanks')
      }
    }

    stage('Publish') {
      steps {
        archiveArtifacts './*'
      }
    }

  }
}