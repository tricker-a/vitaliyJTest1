pipeline {
//  agent any  
  agent {
          label 'dev_lab_2'
  stages {
		stage('Build') {
			steps {
				sh 'npm install'
			}
		}
//		stage('Lint') {
//			steps {
//				sh 'npm run lint'
//			}
//		}
            
		stage('Test') {
			steps {
				sh 'npm run test:ci'
			}
		}
	}
  }
  }
