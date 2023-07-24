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
		deploy adapters: [tomcat9(credentialsId: 'tomcatcreds', path: '', url: 'http://3.82.96.52:8080//')], contextPath: 'Planview', onFailure: false, war: 'target/*.war'
	}
}

  
