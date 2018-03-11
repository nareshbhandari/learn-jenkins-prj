pipeline {
    agent { label 'master' }
    tools { maven 'M3' }
    stages {
        stage("Checkout Stage") {
            steps {
                git 'https://github.com/nareshbhandari/learn-jenkins-prj.git'
            }
        }
        stage("Build Stage") {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage("Test Stage") {
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage("Package Stage") {
            steps {
                sh 'mvn package'
            }
        }
    }
}