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
	sh 'docker build -t th/nodeapp:v1 .'         
        echo 'Build Image Completed'                
      }           
    }	  
    stage('Docker Push') {
    	agent any
      steps {
       script {
      	withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
	}
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push th/nodeapp:v1'
	}
      }
    }
  }  
}
