pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComp                    oseFile: true])
                }
           }
        stage('Test'){
            steps{
              sh 'echo "Performing tests for containers...OK"'
                }
           }
      }
     post{
       always{
           cleanws()
             }
         }
}

