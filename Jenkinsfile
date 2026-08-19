pipeline {
    agent { label 'agent1' }
    stages {
        stage('local setup') {
            steps {
                sh 'node --version'
                sh 'npm --version'
                sh 'zowe --version'
                sh 'zowe plugins list'
                sh '. /home/user1/workspace/venv/bin/activate'
                // sh 'python3.10 -m pip install --no-index --find-links ./duty-offline-install/wheelhouse-linux-py310/ duty==1.9.0 dotmap==1.3.30'

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
