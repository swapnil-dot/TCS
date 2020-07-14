pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
              sh 'docker-compose –f build-compose.yml run –rm compile'
                }
           }
        
     }
     post{
       always{
           cleanWs()
             }
         }
}
