pipeline {
  agent any
  stages {
    stage('checkout') {
    steps {
		git branch: 'main', credentialsId: 'cfb52330-0007-4513-8d3e-ccf5564edf98', url: 'https://github.com/fiend2/Pratice.git'	
    }
  }
   stage('compile stage') {
	  steps {
	    with maven (maven : 'maven_3.8.3') {
		  sh 'mvn clean compile'
		}
	}
  }
  stage('testing') {
	  steps {
	    with maven (maven : 'maven_3.8.3') {
		  sh 'mvn test'
		}
	}
  }
  stage('deployment') {
	  steps {
	    with maven (maven : 'maven_3.8.3') {
		  sh 'mvn deploy'
		}
	}
  }
  
  }
  }
  
