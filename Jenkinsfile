pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-app-1.0-snapshot')
                    docker.withRegistry('https://index.docker.io/v1/', 'tejasudarshan58') {
                        sh 'docker push tejasudarshan58/my-app-1.0-snapshot'
                    }
                }
            }
        }
        // Add more stages as needed
    }
    // Add post-build actions as needed
}

