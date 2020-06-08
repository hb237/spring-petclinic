pipeline {
    agent {
        docker {
            image 'maven:3.6.1-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -Dcheckstyle.skip -DskipTests clean package' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker build -tag h8a1/spring-petclinic'
                sh 'docker run --publish 8000:8080 --detach h8a1/spring-petclinic'
            }
        }
    }
}
