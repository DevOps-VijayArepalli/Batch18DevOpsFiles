node
{

 def mavenHome = tool name: "maven3.6.2"
 
 properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
 
 
 stage('Checkout')
 {
 git branch: 'development', credentialsId: 'ae811390-96d9-45f6-88ad-878cdfbd22e7', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
 }
 
 stage('Build')
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 
 /*
 stage('ExecuteSonarQubeReport')
 {
 sh "${mavenHome}/bin/mvn sonar:sonar"
 
 }
 
 stage('UploadArtifactsIntoNexus')
 {
 sh "${mavenHome}/bin/mvn deploy"
 
 }
 
 stage('DeployAppIntoTomcatServer')
 {
 sshagent(['12909443-b55f-4209-bdba-105eb98fbbfe']) {    
	 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.232.34.217://opt/apache-tomcat-9.0.33/webapps/"
 }
 }
 
 stage('EmailNotification')
 {
 emailext body: '''Build is over!!

 Regards,
 Mithun Technologies,
 9980923226.''', subject: 'Build is over!!', to: 'devopstrainingblr@gmail.com'
 
 }
 
 */

}
