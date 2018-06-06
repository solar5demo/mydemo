pipeline {
    agent { docker { image 'appropriate/curl' } }
    stages {
        stage('build') {
            steps {
                sh '''
                    echo "Update Project Server Task Completion Percentage"
                    ls -lah
                   curl -X PUT http://101.200.195.49:8102/api/ProjectTasks -H 'Content-Type: application/json' -d '[
  {
    "TaskName": "项目范围规划",
    "ProjectName": "test-20180605-A01",
    "PercentComplete": 10
  }
]'

                   '''

            }
        }
    }
}
