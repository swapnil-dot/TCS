pipeline{
      agent none{
           stages{
                stage('Deploy'){
                        steps{
                              sh 'dokcer-compose up -d'
                              }
                            }
                         }   
                }              
}
