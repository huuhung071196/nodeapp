pipeline {   
  agent any  
  environment {
    registry = "huuhung071196/test"
    registryCredential = 'dckr_pat_T0gVjuz4Zg0xRDZ4sZCrWQUgyEc'
  }  
  stages {         
    stage('Git Clone') {           
      steps {                
	git branch: 'main', url: 'https://github.com/huuhung071196/nodeapp.git'                 
	echo 'Git Clone Success'            
      }        
    } 
    stage('Build Docker Image') {  
      steps {   
	sh 'sudo docker build -t th/nodeapp:v1 .'         
        echo 'Build Image Completed'                
      }           
    }	  
  }  
}
