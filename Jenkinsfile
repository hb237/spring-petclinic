pipeline {
agent any
stages {
    stage('Clone') {
        steps {
            git branch: 'master', url: 'https://github.com/hb237/spring-petclinic.git'
            stash name:'scm', includes:'*'
        }
    }

    stage('Build in Docker') {
        steps {
            unstash 'scm'
            script{
                docker.image('maven:3.5.2').inside{ 
                    sh 'pwd'
                    sh 'mvn -v'
                    sh 'mvn clean install'
                }
            }
        }
    }
}
}
