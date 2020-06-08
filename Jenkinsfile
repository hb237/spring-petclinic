pipeline {
    agent any 
    stages {
        stage('Build Jar') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
