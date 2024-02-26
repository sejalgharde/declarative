pipeline {
	agent any 
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/sejal/Documents/devops-software/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/declarative.war /home/sejal/Documents/devops-software/apache-tomcat-9.0.85/webapps'
			}}
		stage('slack notification') {
		   steps {
	        slackSend baseUrl: 'https://hooks.slack.com/services/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/', channel: '#devops-slack', color: 'good', message: 'this  is for test', teamDomain: 'student', tokenCredentialId: 'slacktest'
		        }}
}}
