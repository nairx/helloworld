pipeline {
    agent any
    tools {
        jdk 'JDK21'
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
            git branch: 'main',
                url: 'https://github.com/nairx/helloworld.git'
    }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                bat 'copy target\\helloworld-1.0-SNAPSHOT.jar D:\\hello-world\\hello.jar'
            }
        }
        stage('Run Application') {
            steps {
                bat '''
                taskkill /F /IM java.exe || exit 0
                start java -jar D:\\hello-world\\hello.jar
                '''
            }
        }
    }
}

