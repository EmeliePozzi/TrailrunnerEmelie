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
                // Navigate to the Maven project directory and build it
                dir('labb2') {
                    bat 'mvn clean install'
                }
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
