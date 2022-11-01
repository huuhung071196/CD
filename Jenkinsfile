pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/huuhung071196/CD.git'
            }
           }
        stage('Syn github') {
            steps {
                ansibleTowerProjectSync async: false, importTowerLogs: false, project: 'github', removeColor: false, throwExceptionWhenFail: false, towerCredentialsId: 'aaff4ece-0831-4f9a-abf1-d4dd7ae4bea2', towerServer: 'ansible-AWX', verbose: false
            }
           } 
        stage('run playbook') {
            steps {
                ansibleTower jobTemplate: 'test-gcp', jobType: 'run', throwExceptionWhenFail: false, towerCredentialsId: 'aaff4ece-0831-4f9a-abf1-d4dd7ae4bea2', towerLogLevel: 'false', towerServer: 'ansible-AWX'
            }
           } 
    }
}
