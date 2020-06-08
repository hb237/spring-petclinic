pipeline {
    agent {
        docker {
            image 'maven:3.6.1-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build Jar') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
