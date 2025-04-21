pipeline {
    agent {label 'slave-1'}
    
    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

    stages {
        stage('Compile') {
            steps {
                sh "mvn compile"
            }
        }
        stage('test') {
            when {
                changeset "src/test/java/com/javaproject/TestController.java"
            }
            steps {
                sh "mvn test"
            }
        }
        stage('Build') {
            steps {
                sh "mvn package"
            }
        }
    }
}
