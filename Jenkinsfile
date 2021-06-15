agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'http://gsgit.gslab.com/dipti_bagal/Jenkins.git'
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
          junit 'test-reports/*.xml'
        }
      }
    }
  }
}
