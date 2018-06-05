pipeline {
    agent { docker { image 'appropriate/curl' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                   curl -X PUT   http://101.200.195.49:8102/api/ProjectTasks   -H 'Content-Type: application/json'   -d '[
  {
    "TaskName": "项目范围规划",
    "ProjectName": "test-20180605-A01",
    "PercentComplete": 8
  }
]'

                   '''

            }
        }
        stage('Test') {
            steps {
                sh 'echo "Fail!"; exit 1'
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
