// node {
//     stage('Build') {
//         echo 'Building...'
//     }
//     stage('Test') {
//         echo 'Testing...'
//     }
//     stage('Deploy') {
//         echo 'Deploying...'
//     }
// }


// 


pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'bash build.sh'
            }
        }
        stage('Test') {
            steps {
                sh 'bash test.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh 'bash deploy.sh'
            }
        }
    }

    post {
        success {
            echo "🎉 Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed!"
        }
        always {
            archiveArtifacts artifacts: '*.log', fingerprint: true
            echo "📦 Logs have been archived."
        }
    }
}
