pipeline {
    agent {
    label "devopstest"
  }
    stages {
        stage('Verify installation') {
            steps {                
                    sh '''
                    docker --version
                    docker info
                    docker compose version
                    curl --version
                    jq --version
                    '''                
            }
        }
        stage('Check container is running or not'){
            steps {
                sh 'docker ps'
                sh 'docker ps -a'
            }
        }
        stage('starting container'){
            steps{
                sh 'docker compose up -d --no-color --wait'
                sh 'docker compose ps'
            }
        }
        
    }

}
