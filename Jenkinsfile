pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
        jdk 'openjdk-11'
    }
    stages {
        stage ('Build') {
            steps {
                sh 'mvn -DskipTests install' 
                sh 'java -jar target/*.jar'
            }
        }
    }
}
