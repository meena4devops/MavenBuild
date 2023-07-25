node(){

	
	
	stage('Code Checkout'){
		checkout scm
	}
	stage('Build'){
		sh "mvn clean install"
	}


	
	stage('archiveArtifacts'){
		
			archiveArtifacts artifacts: 'target/*.war'
		
		
	}

    	stage('teststage'){
		
			echo 'testing' 
		
		
	}
	
	stage('Code Deployment'){
		
		deploy adapters: [tomcat9(credentialsId: 'tomcatcreds', path: '', url: 'http://52.87.229.39:8080/')], contextPath: Planview, war: '**/*.war'
	}
}

  
