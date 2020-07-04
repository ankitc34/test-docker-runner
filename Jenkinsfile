pipeline{
    agent any
	stages{
	   stage("Start Grid"){
	      steps{
		    bat "docker-compose up -d hub chrome firefox --no-color"
		  }
	   }
	   stage("Run Test"){
	     steps{
		    bat "docker-compose up book-flight-module search-module --no-color"
		 }
	   }
	   stage("Bring Grid Down"){
	      steps{
		    bat "docker-compose down"
		  }
	   }
	}

}