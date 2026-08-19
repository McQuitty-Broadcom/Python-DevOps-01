pipeline {
    agent { label 'agent1' }
    stages {
        stage('local setup') {
            steps {
                sh 'node --version'
                sh 'npm --version'
                sh 'zowe --version'
                sh 'zowe plugins list'
        }
        }
        stage('build') {
            steps {
                    sh 'duty build'
            }
        }
        stage('deploy') {
            steps {
                    sh 'duty deploy'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'output/**/*.*' 
        }
    }
}
