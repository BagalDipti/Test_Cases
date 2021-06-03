pipeline {
  environment {
        registry = "diptibagal3010"
        dockerImage = ''
        Name = "flask"
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/BagalDipti/Test_Cases.git'
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + "/" +Name+":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '' ) {
            dockerImage.push()
          }
        }
      }
    }
    stage('Docker Run') {
        steps {
          script {
            sh "docker rm Flask-App --force"

              dockerImage.run(" -p 5001:5001 --rm --name Flask-App")
          }
        }

    }

  }
}
