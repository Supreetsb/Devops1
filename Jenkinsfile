pipeline {
    agent {
        docker {
            image 'my-app-1.0-SNAPSHOT'
            args '-u root'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-app-1.0-SNAPSHOT .'
                sh 'docker login'
                sh 'docker push tejasudarshan58/my-app-1.0-SNAPSHOT'
'
            }
        }
        // Add more stages as needed
    }
    // Add post-build actions as needed
}
