pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw clean'
      }
    }

    stage('Test') {
      steps {
        sh './mvnw test'
      }
    }

    stage('Package') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Deploy') {
      when {
        branch 'master'
      }
      steps {
        echo '"Deployed"'
      }
    }

  }
  post {
    always {
      emailext(subject: 'PetClinic Build Status', body: 'Build finished!', attachLog: true, from: 'vivekaanban@gmail.com', to: 'viveka98@hotmail.ca')
    }

  }
}
