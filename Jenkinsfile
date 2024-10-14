pipeline {
    agent any
    
    tools {
        jdk 'jdk8'
    }
    
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/tuan-devops/cicd-pipeline-train-schedule-dockerdeploy'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh 'chmod +x ./gradlew && ./gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
