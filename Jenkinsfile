pipeline {   
  agent any  
  stages {         
    stage("Git Clone") {           
      steps {                
	git branch: 'main', url: 'https://github.com/huuhung071196/nodeapp.git'                 
	echo 'Git Clone Success'            
      }        
    } 
    stage('Build Docker Image') {         
      steps {                
	sh 'sudo docker build -t huuhung071196/nodeapp .'           
        echo 'Build Image Completed'                
      }           
    }	  
  }  
}
