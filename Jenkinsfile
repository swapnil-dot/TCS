pipeline{
    node{
         stage(‘Build’) {
      sh ‘docker-compose –f build-compose.yml run –rm compile’
    }
    stage(‘Test) {
      sh ‘docker-compose –f build-compose.yml run –rm test’
    }
    }
}
