pipeline{
agent any
stages{
stage("Pull Latest Image"){
			steps{
      cleanWs()
				sh "docker pull codingeton/selenium-docker"
			}
		}
  stage("Start Grid"){
    steps{
      sh "docker-compose up -d hub chrome firefox"
    }
  }

  stage("Run Test"){
    steps{
      sh "docker-compose up search-module"
    }
  }
}
post{
always{
archiveArtifacts artifacts: 'output/**'
sh "docker-compose down"
}
}
}
