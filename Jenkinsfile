pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
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
            deleteDir() /* clean up our workspace */
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

                     
