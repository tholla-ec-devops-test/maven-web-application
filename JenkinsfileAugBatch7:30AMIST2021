node 
{
    def mavenHome = tool name: "maven3.6.2"
  stage('CheckOutCode'){
 git branch: 'development', credentialsId: 'deaf22c6-86f5-4e40-85de-23f11bd1acc3', url: 'https://github.com/tholla-ec-devops-test/maven-web-application.git'
      }
	stage('Build'){
	sh "${mavenHome}/bin/mvn clean package"
	}
  /*
	stage('ExecuteSonarQubeReport'){
	sh "${mavenHome}/bin/mvn clean sonar:sonar"
	}
	stage('UploadArtifactIntoNexusRepo'){
	sh "${mavenHome}/bin/mvn clean deploy"
	}
    stage('DeploytheAppintoTomcat'){
	sshagent(['13ba43ca-5441-41da-a8ea-b723e817e9f1']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.235.78.98:/opt/apache-tomcat-9.0.53/webapps"
	}
	}
  */
	stage('SendEmailNotification'){
	mail bcc: 'tholla.venu@gmail.com', body: '''Build Over!!!

    Regards,
    Venu Gopal''', cc: 'tholla.venu@gmail.com', from: '', replyTo: '', subject: 'Build Over!!!', to: 'tholla.venu@gmail.com'
	}
 
    

}	
	
