pipeline {
	agent any 
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/sejal/Documents/devops-software/apache-tomcat-9.0.85/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/declarative.war /home/sejal/Documents/devops-software/apache-tomcat-9.0.85/webapps'
			}}	
}}
