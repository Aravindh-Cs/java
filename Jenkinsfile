pipeline {
    agent any

    tools {
        jdk 'JDK'
        maven 'Maven'
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
                "C:\\Users\\2msccsa02\\Downloads\\apache-tomcat-9.0.115-windows-x64\\apache-tomcat-9.0.115\\webapps\\"
                '''
            }
        }
    }
}
