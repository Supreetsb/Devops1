pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-app-1.0-snapshot')
                    docker.withRegistry('https://tejasudarshan58', 'tejasudarshan58') {
                        sh 'sudo docker push tejasudarshan58/my-app-1.0-snapshot'
                    }
                }
            }
        }
        // Add more stages as needed
    }
    // Add post-build actions as needed
}

