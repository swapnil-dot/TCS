pipeline{
    agent any
    stages{
        stage('SCM CheckOut'){
          steps {
            git 'https://github.com/swapnil-dot/TCS.git'
          }
          }
        stage('Docker-compose'){
           steps{
             step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
             step{
                   sh 'docker-compose up -d'
               }
                }
           }
        
      }
     post {
        always {
            echo 'One way or another, I have finished'
            /* clean up our workspace */
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}

                     
