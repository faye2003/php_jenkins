groovy
pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/username/repository.git'
    }
  }
  stage('Install Dependencies') {
    steps {
      bat 'composer install'
    }
  }
  stage('Run Tests') {
    steps {
      bat 'php artisan test'
    }
  }
  stage('Static Analysis') {
    steps {
      bat 'vendor/bin/phpcs --standard=PSR2 app/'
    }
  }
  stage('Build') {
    steps {
      // Si vous avez une étape de build pour Laravel, vous pouvez l'ajouter
      ici.
    }
  }
}
  post {
    always {
    archiveArtifacts artifacts: '**/storage/logs/*.log', allowEmptyArchive:
    true
    junit 'tests/_output/*.xml'
    }
  }
}