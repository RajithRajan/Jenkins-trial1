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
        writeFile(file: 'outputfile.txt', text: 'testing the write function')
        archiveArtifacts 'outputfile.txt'
      }
    }

    stage('Trigger') {
      steps {
        build 'firstjob'
      }
    }

  }
}