node(){

	
	
	stage('Code Checkout 4 KALPANA'){
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

	stage('teststage 4 CODE SCANNING DEMO FOR Kalpana'){
		
			echo 'kalpana code scanning at github' 
		
		
	}
	
	stage('Code Deployment'){
		
		deploy adapters: [tomcat9(credentialsId: 'kalpana', path: '', url: 'http://54.235.51.42:8080//')], contextPath: 'KALPANADEMO', war: 'target/*.war'
	}
}

  
