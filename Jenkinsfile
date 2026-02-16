pipeline {
    agent any

    tools {
        jdk 'JDK11'
        maven 'Maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build WAR') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                bat '''
                copy /Y target\\java.war "C:\\Users\\2msccsa02\\Downloads\\apache-tomcat-9.0.115-windows-x64\\apache-tomcat-9.0.115\\webapps\\"
                '''
            }
        }
    }
}
