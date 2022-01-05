pipeline {
//  agent any
//  checkout(
//         [$class: 'GitSCM',
//         branches: [[name: '*/master']],
//         extensions: [[$class: 'PreBuildMerge',
//         options: [mergeStrategy: 'RECURSIVE_THEIRS',
//                   mergeTarget: 'master']]],
//          userRemoteConfigs: [[credentialsId: 'j14', url: 'https://github.com/vitaliykremez/vitaliyJTest1.git']]]
//  )
  triggers {
    cron (BRANCH_NAME == "master" ? "0 2 * * *" : "")
  }
  agent {label 'dev_lab_2'}
  stages {
		stage('install') {
			steps {
        sh 'npm install || ls || pwd'
			}
		}
/*		stage('Lint') {
			steps {
				sh 'npm run lint'
			}
		}
*/
		stage('Test') {
			steps {
				sh 'npm run test:ci'
         sleep 15

			}
		}
    stage('Build') {
			steps {
				sh '''
          npm run build
          pwd && ls -l
          ls -la "dist/TestProjectJenkins/"
          ls -la "/var/www/TestProjectJenkins/"
        '''
        archiveArtifacts artifacts: 'dist/TestProjectJenkins/*', followSymlinks: false, onlyIfSuccessful: true
          chuckNorris()
      }
		}

    stage('deploy') {
      when { branch 'master' }
			steps {
				sh '''
          cp -R dist/TestProjectJenkins/* "/var/www/TestProjectJenkins/"
          ls -la "/var/www/TestProjectJenkins/"
        '''
			}
		}
	}
}
