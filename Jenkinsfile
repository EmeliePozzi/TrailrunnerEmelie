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
                dir('labb2') {
                    //Genom att lägga bygget i ett script-block låter jag Jenkins välja att köra bat eller sh-kommandot baserat på operativsystem.
                    script {
                        sh 'mvn clean install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                dir('labb2') {
                    script {
                        sh 'mvn test'
                    }
                }
            }
        }
        stage('Post Test') {
            steps {
                dir('labb2') {
                    script {
                        junit '**/target/surefire-reports/*.xml'
                    }
                }
            }
        }
    }
}
