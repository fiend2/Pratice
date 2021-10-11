pipeline {
	agent any
  stages {
    stage('checkout') {
    steps {
	  checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[credentialsId: 'cfb52330-0007-4513-8d3e-ccf5564edf98', url: 'https://github.com/fiend2/Pratice.git']]])
	}
  }
  
  
  
    stage('Build') {
	  steps {
	    build 'testing_pipeline'
	    echo "Build"
	}
  }
  }
  
}
