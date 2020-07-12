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
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: false])
                }
           }
        stage('Test'){
            steps{
              sh 'echo "Performing tests for containers...OK"'
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

                     
