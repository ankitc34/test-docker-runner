pipeline{
    agent any
	stages{
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
	   stage("Bring Grid Down"){
	      steps{
		    bat "docker-compose down"
		  }
	   }
	}

}