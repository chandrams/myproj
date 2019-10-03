pipeline {
    environment {
        registry = "chandrams/cbolt"
        registryCredential = ''
        dockerImage = 'cbolt'
    }
    agent any 
        stages {
	    stage ('Git clone repo') {
	        steps {
		    echo "Get cbolt Git repo..."
		    git "https://github.ibm.com/chandra-ms/cbolt.git"


	        }
	    }
	    stage ('Build image') {
		steps {
		    script {
		        dockerImage=docker.build("cbolt")
		    }
	        }
	    }
	    stage ('Test image') {
		steps {
		    script {
		        dockerImage.inside {
			    echo 'inside image'
		        }
		    }
		}
	    }	


	}
}
