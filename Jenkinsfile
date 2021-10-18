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

	stage('SonarQube analysis') {
	steps {
              withSonarQubeEnv('sonar_7.1') {
              sh 'mvn clean package sonar:sonar'
			  }
		}
	}
	   
  stage('deployment') {
	  steps {
		  sh 'mvn deploy'
	}
  }
  }
  }
