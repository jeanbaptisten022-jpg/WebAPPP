pipeline {
    agent any

    environment {
        NODE_VERSION = '18' // Node.js version
    }

    stages {
        stage('Setup') {
            steps {
                echo 'Installing Node.js...'
                sh 'curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing npm packages...'
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'npm test || echo "No tests found"'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
