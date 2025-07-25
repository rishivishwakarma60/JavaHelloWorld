pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/rishivishwakarma60/JavaHelloWorld', branch: 'main'
            }
        }

        stage('Compile Java') {
            steps {
                echo '🔧 Compiling Java...'
                sh 'mkdir -p build'
                sh 'javac -d build src/HelloWorld.java'
            }
        }

        stage('Run Java Program') {
            steps {
                echo '🚀 Running Java Program...'
                sh 'java -cp build HelloWorld'
            }
        }

        stage('Archive Class File') {
            steps {
                archiveArtifacts artifacts: 'build/HelloWorld.class', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful!'
        }
        failure {
            echo '❌ Build Failed!'
        }
    }
}
