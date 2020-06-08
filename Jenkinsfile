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
                sh 'mvn -B -Dcheckstyle.skip -DskipTests clean package' 
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'mvn jar:jar install:install help:evaluate -Dexpression=project.name'
                    sh 'NAME=`mvn help:evaluate -Dexpression=project.name | grep "^[^\[]"`'
                    sh 'VERSION=`mvn help:evaluate -Dexpression=project.version | grep "^[^\[]"`'
                    sh 'java -jar target/${NAME}-${VERSION}.jar'
                }
            }
        }
    }
}
