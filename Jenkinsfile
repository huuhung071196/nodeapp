pipeline {   
  agent any  
  environment {
    DOCKERHUB_CREDENTIALS= credentials('dockerHub')
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
	sh 'docker build -t huuhung071196/nodeapp:v1 .'         
        echo 'Build Image Completed'                
      }           
    }	  
    stage('Login to Docker Hub') {         
      steps {                            
	sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                 
	echo 'Login Completed'                
      }           
    }   
    stage('Push Image to Docker Hub') {         
      steps {                            
	sh 'docker push huuhung071196/nodeapp:v1'                 
        echo 'Push Image Completed'
	sh 'docker image rm huuhung071196/nodeapp:v1'
      }    
    }      
  } //stages
  post {
    always {  
      sh 'docker logout'           
    }      
  }  
} //pipeline
