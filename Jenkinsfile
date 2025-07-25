pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/rishivishwakarma60/JavaHelloWorld'
            }
        }

        stage('Compile Java') {
            steps {
                echo '🔧 Compiling Java...'
                bat 'javac HelloWorld.java'
            }
        }

        stage('Run Java Program') {
            steps {
                echo '🚀 Running Java Program...'
                bat 'java HelloWorld'
            }
        }

        stage('Archive Class File') {
            steps {
                archiveArtifacts artifacts: '*.class', fingerprint: true
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
