pipeline {
    agent any
    stages {
        stage ('1-Git-Clone') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCredentials', url: 'https://github.com/etechapp/parallel-mulitbranch-pipeline.git']]])
            } 
        }
        stage ('2-Parallel-Jobs') {
            parallel {
                stage ('sub-job-1') {
                    steps {
                        sh 'lscpu'
                    }
                }
            }
        }
    }
}