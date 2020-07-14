pipeline{
      agent docker{
           stages{
                stage('Deploy'){
                        steps{
                              step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
                              }
                            }
                         }   
                }              
}
