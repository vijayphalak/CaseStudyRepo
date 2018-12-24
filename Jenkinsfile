pipeline {
	agent any
	stages{
		stage('Deployment to development server'){
			steps{
				build 'Development'
			}
		}
		stage('Approval for deploying on test server'){
			steps{
				timeout(time:2,unit:'DAYS'){
					input message:'Please approve this request for deployment on test server',submitter:'vijayphalak'
				}
			}
		}
		stage('Deployment to testing server'){
			steps{
				build 'Testing'
			}
		}
		stage('Approval for deploying on production server'){
			steps{
				timeout(time:2,unit:'DAYS'){
					input message:'Please approve this request for deployment on production server',submitter:'vijayphalak'
				}
			}
		}
		stage('Deployment to production server'){
			steps{
				build 'Production'
			}
		}
	}
}