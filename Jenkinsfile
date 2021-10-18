pipeline {
  agent any
	tools {
	   maven 'maven_3.6.3'
	}
	
  stages {
   /* stage('checkout') {
    steps {
		git branch: 'main', credentialsId: 'cfb52330-0007-4513-8d3e-ccf5564edf98', url: 'https://github.com/fiend2/Pratice.git'	
    }
  }*/
   stage('compile stage') {
	  steps {
		  sh 'mvn clean compile'
	}
  }
  
  stage('testing') {
	  steps {
		  sh 'mvn test'
	}
  }																												
  stage('deployment') {
	  steps {
		  sh 'mvn deploy'
	}
  }
   stage('Upload War To Nexus') {
	  steps {
		  nexusArtifactUploader credentialsId: 'nexus', 
		  groupId: 'Steam', 
		  nexusUrl: '18.237.21.104:8081', 
		  nexusVersion: 'nexus3', 
		  protocol: 'http', 
		  repository: 'target/Dota', 
		  version: '1.0.0'
  }
  }
  }
  }
