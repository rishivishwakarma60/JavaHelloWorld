pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/rishivishwakarma60/JavaHelloWorld'
            }
        }

        stage('Compile Java') {
            steps {
                echo '🔧 Compiling Java...'
                bat 'javac src\\HelloWorld.java'
            }
        }

        stage('Run Java Program') {
            steps {
                echo '🚀 Running Java Program...'
                bat 'java -cp src HelloWorld'
            }
        }

        stage('Archive Class File') {
            steps {
                archiveArtifacts artifacts: 'src\\*.class', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Build Succeeded!'
        }
        failure {
            echo '❌ Build Failed!'
        }
    }
}
