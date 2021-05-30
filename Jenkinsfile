pipeline {
	agent any
	//Can be declared at pipeline or stage level and will be available accordingly.

	environment {
	    OUTPUT_PATH = './output/'
	}
    tools {
        maven 'maven3'
    }

    //Defined at both pipeline and Stage level. But both level option are diffirent.
    options {
        timeout(time: 1, unit: 'HOURS') 
    }

	
	stages {
		
	    stage ('Cleanworkspace') {
	        steps {
				cleanWs()		
	        }
	    }
		
	    // stage ('Input') {
        //     //Input is defined at stage level and variables are available on stage level only.
		//     input {
		// 	message "Press OK to Continue"
		// 	parameters{
		// 	    string(name:'username', defaultValue: 'User', description: 'Username of the user pressing Ok')
		// 	    string(name:'Number',defaultValue:'one')
		// 			}
		// 	    }
		// 	steps{
		// 		sh 'echo "Input Stage"'
		// 		sh 'echo "Username is ${username} and number is ${Number}"'
		// 		}
	    // }
		
		
	    stage ('Environment Variable') {
	        steps {
	            sh 'echo ${OUTPUT_PATH}'
	            
	        }
	    }
		stage ('build') {

		    steps {
		        sh 'mvn -version'
		    }
			
		}

	}

    post {
        always {
            echo "Pipeline completed"
        }
    }
}
