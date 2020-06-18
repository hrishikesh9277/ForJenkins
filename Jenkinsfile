/*pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
*/


/* added line*/
pipeline{
	agent none
		stages{
		stage('Non-parallel'){
		   agent{
		            label 'master'
		        }
		   steps{
		    echo "This will be executed first, a non-parallel stage";
		        }
		                      }
		        
		stage('Run tests parallel'){        
		  parallel{
		       stage('Tests On Windows'){
		            agent{
		                    label 'Slave1'
		                 }
		              steps{
		                  echo "Running tests on windows";
		                   }   
		                                  }
		        stage('Tests on linux'){
		            agent{
		                    label 'master'
		                 }
		            steps{
		                    echo "Running tests on linux";
		                 }       
		                                }                            
		                
		            }      
}                     
}
}