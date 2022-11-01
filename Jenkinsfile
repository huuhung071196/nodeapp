pipeline {   
  agent any
  environment {     
    DOCKERHUB_CREDENTIALS= credentials('dckr_pat_JFl_5KFZo20oBydg-QN85peT51E')     
  }    
  stages {         
    stage("Git Clone"){           
      steps{                
	git branch: 'main', url: 'https://github.com/huuhung071196/nodeapp.git'                 
	echo 'Git Clone Completed'            
      }        
    }
    stage('Build Docker Image') {         
      steps{                
	sh 'sudo docker build -t huuhung071196/nodeapp:$BUILD_NUMBER .'           
        echo 'Build Image Completed'                
      }           
    }  
  }  
}
