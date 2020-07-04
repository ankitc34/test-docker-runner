pipeline{
    agent any
	stages{
	   stage("pull latest Image"){
	      steps{
		    bat "docker pull ankitc34/test-docker:latest"
		  }	   
       }
	   stage("Start Grid"){
	      steps{
		    bat "docker-compose up -d hub chrome firefox"
		  }
	   }
	   stage("Run Test"){
	     steps{
		    bat "docker-compose up book-flight-module search-module"
		 }
	   }
	}
	post{
	   always{
	      archiveArtifacts artifacts: 'output/**'
		  bat "docker-compose down"
	   }	
	}

}