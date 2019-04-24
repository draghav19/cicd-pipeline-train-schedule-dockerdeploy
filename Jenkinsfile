pipeline {
    agent { dockerfile true }
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage ('Test') {
            steps {
                sh 'echo $(curl localhost:8080)'
            }
        }
        
    }
}
