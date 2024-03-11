pipeline {
    agent any

    stages {
        
        stage('Checkout (Hämtar senaste kodversionen för den valda grenen)') {
            steps {
                git 'https://github.com/EmeliePozzi/TrailrunnerEmelie.git'
            }    
        }
        stage('Build trailrunnerProject') {
            steps {
                dir('labb2') {
                    
                    script {
                        sh 'mvn clean install'
                    }
                }
            }
        }
        stage('Test trailrunnerProject') {
            steps {
                dir('labb2') {
                    script {
                        sh 'mvn test'
                    }
                }
            }
        }
        stage('Post Test from trailrunnerProject') {
            steps {
                dir('labb2') {
                    script {
                        junit '**/target/surefire-reports/*.xml'
                    }
                }
            }
        }
        stage('Run Robot and Post Test') {
            steps {
                dir('Selenium') {
                    script {
                        sh 'robot test.robot'
                    }
                }
            }
            post {
                always {
                    dir('Selenium/log') {
                        junit 'output.xml'
                    }
                }
            }
        }

        
    }
}
