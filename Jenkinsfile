pipeline {
    agent { docker { image 'python:3.6' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'cd /opt/projects/MISA.CvExtraction'
                sh 'docker-compose build cvextract-hrm'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Success!"'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}