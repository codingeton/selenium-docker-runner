pipeline{
agent any
stages{
  stage("Start Grid"){
    steps{
    withEnv(["PATH=$PATH:~/.local/bin"]){
      sh "docker-compose up -d hub chrome firefox"
    }
  }
  }
  stage("Run Test"){
    steps{
      sh "docker-compose up search-module"
    }
  }
  stage("Stop Grid"){
    steps{
      sh "docker-compose down"
    }
  }
}
}
