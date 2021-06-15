agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/BagalDipti/Test_Cases.git'
      }
    }
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit '/*.xml'
        }
      }
    }
  }
}
