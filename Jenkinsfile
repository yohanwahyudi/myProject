pipeline {
    agent { label 'jenkins-node1' }
    tools {
        maven 'maven-3.8.4'
    }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/yohanwahyudi/myProject.git'
          }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
