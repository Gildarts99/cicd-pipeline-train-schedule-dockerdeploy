pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'building docker image'
                sh 'cd /var/lib/jenkins/workspace/train_schedule_master-66CKD2BQYUPTV6GKTONHHEJPKSM7T2PI72D5DPCNHRV5SHFUIRHA'
                sh 'docker build -t gildarts99/cicd-pipeline .'
            }
        }
    }
}
