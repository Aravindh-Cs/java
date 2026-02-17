pipeline {
    agent any

    tools {
        jdk 'JDK'
        maven 'MAVEN'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build WAR') {
            steps {
                bat 'mvn -f java\\pom.xml clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                bat '''
                copy /Y java\\target\\java.war ^
                "C:\\appache\\apache-tomcat-9.0.115\\webapps\\"
                '''
            }
        }
    }
}
