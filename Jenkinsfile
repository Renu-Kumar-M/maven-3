pipeline {
    agent any

    environment {
       
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-21.0.12.1'
        PATH = "${env.JAVA_HOME}\\bin;${env.PATH}"
    }

    tools {
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                
                git branch: 'main', url: 'https://github.com/Renu-Kumar-M/maven-3.git'
            }
        }
        stage('Package') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Run JAR') {
            steps {
                bat 'java -cp target\\maven-package-demo-1.0.jar com.example.App'
            }
        }
    }
}
