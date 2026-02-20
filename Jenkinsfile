pipeline {
    agent any

    tools {
        maven 'Maven'   // must match Jenkins Global Tool name
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/prath1234/hello-maven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/hello-maven-1.0-SNAPSHOT.jar'
            }
        }
    }
}
