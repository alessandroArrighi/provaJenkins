pipeline {
    agent {
        docker { image 'gradle' }
    }
    
    stages {
        stage('prova') {
            steps {
                sh 'gradle --version'
            }
        }
    }
}
