//Declarative way
pipeline {
    agent any

    stages {
        stage('build') {
            steps {
		echo "My Branch Name: ${env.BRANCH_NAME}"
                bat 'ant -f build.xml'
	    }
	}
    }
	
	post {
        success {
          emailext(
	   subject: "${env.JOB_NAME} [${env.BUILD_NUMBER}] Successfull",
           body: "${env.JOB_NAME} [${env.BUILD_NUMBER}] ${env.BUILD_URL}",
		  to: "${env.DEFAULT_RECIPIENTS},devopstrainingblr@gmail.com,parthureddy1159@gmail.com"
          )
        }
	failure{
	   emailext(
	   subject: "${env.JOB_NAME} [${env.BUILD_NUMBER}] Failed",
           body: "${env.JOB_NAME} [${env.BUILD_NUMBER}] ${env.BUILD_URL}",
		   to: "${env.DEFAULT_RECIPIENTS},devopstrainingblr@gmail.com,parthureddy1159@gmail.com"
            )		   
		}
      }
	
}
