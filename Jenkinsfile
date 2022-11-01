pipeline {
    agent any
    stages {
        stage('git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/huuhung071196/nodeapp.git'
            }
           }
	stage('connect docker hub') {
            steps {
                withDockerRegistry(credentialsId: '03ed810a-e438-40b6-8af8-b60a79e142c0', url: 'https://index.docker.io/v1/')
            }
           }    
        stage('Build') {
            steps {
                sh 'docker build -t huuhung071196/nodeapp .'
            }
           } 
	stage('Push') {
            steps {
		sh 'docker push huuhung071196/nodeapp'
             }
	   }
	 post {
		always {
			sh 'docker logout'
	     }
           }   
	 
    }
}
