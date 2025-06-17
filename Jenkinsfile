pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    tools {
        maven 'Maven 3.8.6'
        jdk 'JDK11'
    }

    stages {
        stage('Clonar') {
            steps {
                git branch: 'main', url: 'https://github.com/Benyii/saludoapp.git'
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo "🎉 El build fue exitoso"
        }
        failure {
            echo "💥 El build falló"
        }
    }
}
