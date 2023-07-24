node(){

	def sonarHome = tool name: 'SonarScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
	
	stage('Code Checkout'){
		checkout scm
	}
	stage('Build'){
		sh "mvn clean install"
	}

    stage('Code Scan'){
		withSonarQubeEnv(credentialsId: 'SonarQubeCreds') {
			sh "${sonarHome}/bin/sonar-scanner"
		}
		
	}
	
	stage('archiveArtifacts'){
		
			archiveArtifacts artifacts: 'target/*.war'
		
		
	}
	
	stage('Code Deployment'){
		deploy adapters: [tomcat9(credentialsId: 'tomcatcreds', path: '', url: 'http://3.82.96.52:8080//')], contextPath: 'Planview', onFailure: false, war: 'target/*.war'
	}
}

  
