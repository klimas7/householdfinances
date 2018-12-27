pipeline {
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '10')
    }
    triggers {
        pollSCM ''
    }
    agent {
        docker {
            image 'maven:3.6.0-jdk-11-slim'
            args '-v /root/.m2:~/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}