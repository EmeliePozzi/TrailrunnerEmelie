pipeline {
    agent any

    stages {
        
        stage('Checkout (Hämtar senaste kodversionen för den valda grenen)') {
            steps {
                git 'https://github.com/EmeliePozzi/TrailrunnerEmelie.git'
    }
}
        stage('Build') {
            steps {
                 bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
