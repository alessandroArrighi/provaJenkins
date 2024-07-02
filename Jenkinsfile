pipeline {
    agent {
        docker { image 'gradle' }
    }
    
    stages {
        stage('SCM') {
            steps {
                git url: 'https://github.com/alessandroArrighi/provaJenkins', branch: "main"
            }
        }
        stage('Build con Sonar') {
            steps {
                withSonarQubeEnv('SonarQubeProva') { // Will pick the global server connection you have configured
                    sh "gradle sonar -Dsonar.projectKey=prova -Dsonar.projectName='prova' -Dsonar.token=sqp_19beff97dfb8ce2cbb49eaad2a8817fe80507f0c"
                }
            }
        }
        
    }
}
