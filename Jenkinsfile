pipeline {

	agent any

	environment {
		//docker_credentials = credentials('docker_credentials')
	//	docker_repo = 'https://hub.docker.com/repository/docker/spadevapps/sba.casestudy'
		git_repo = 'https://github.com/spadevapps/2020_03_DO_Boston_casestudy_part_1'
	}

	stages {
    stage('clone repo') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/spadevapps/casestudy2.git']]])
        }
    }

		stage ('deploy') {
			steps {

				ansiblePlaybook(playbook: 'ansible-playbook1.yml')
				//sh 'ansible-playbook ansible-playbook.yml'

			}

		}

	}
}
