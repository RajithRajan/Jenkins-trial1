pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/RajithRajan/Jenkins-trial1.git', branch: '*/*')
      }
    }

    stage('SettingParm') {
      steps {
        sh 'echo \'hello\''
      }
    }

  }
}