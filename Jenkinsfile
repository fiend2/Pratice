pipeline {
  agent any
  stages {
    stage('checkout') {
    steps {
		git branch: 'main', credentialsId: 'cfb52330-0007-4513-8d3e-ccf5564edf98', url: 'https://github.com/fiend2/Pratice.git'	
    }
  }
  
  
  
<<<<<<< HEAD
   stage('compile stage') {
=======
   stage('Build') {
>>>>>>> f46dcbf7e102fd62df1a4598feb2e153cebf7ccb
	  steps {
	    with maven (maven : 'maven_3.8.3') {
		  sh 'mvn clean compile'
		}
	}
  }
<<<<<<< HEAD
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
  
=======
  }  
}

>>>>>>> f46dcbf7e102fd62df1a4598feb2e153cebf7ccb
