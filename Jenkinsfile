pipeline {
    agent {
        docker {
            image 'my-app-1.0-snapshot'
            args '-u root'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'sudo docker build -t my-app-1.0-snapshot .'
                sh 'sudo docker login'
                sh 'sudo docker push tejasudarshan58/my-app-1.0-snapshot'
            }
        }
        // Add more stages as needed
    }
    // Add post-build actions as needed
}
