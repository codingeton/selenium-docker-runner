pipeline{
agent any
stages{
stage("Pull Latest Image"){
			steps{
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
  stage("Stop Grid"){
    steps{
      sh "docker-compose down"
    }
  }
}
}
