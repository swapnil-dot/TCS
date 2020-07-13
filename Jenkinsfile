pipeline{
      agent any{
           stages{
                stage('Deploy'){
                        steps{
                              sh 'dokcer-compose up -d'
                              }
                            }
                         }   
                }              
}
