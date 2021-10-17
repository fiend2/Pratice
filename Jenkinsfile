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
  stage('SonarQube analysis') {
	 withSonarQubeEnv('sonar') {
	 def mvnHome = tool name: 'maven_3.6.3', type: 'maven'
	 sh "${mvnHome}/bin/mvn sonar:sonar"
	 } 
  }
  
  stage('testing') {
	  steps {
		  sh 'mvn test'
	}
  }
  stage('SonarQube analysis 1') {
            steps {
                sh 'mvn clean package sonar:sonar'
            }
        }																												
  stage('deployment') {
	  steps {
		  sh 'mvn deploy'
	}
  }
  }
  }
  
