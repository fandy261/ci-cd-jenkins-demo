pipeline {
    agent {
    label 'master'
     }

    environment {
        APP_DIR = 'mini-node-app'
    }

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token-fandy',
                    url: 'https://github.com/fandy261/ci-cd-jenkins-demo.git',
                    branch: 'main'
            }
        }

	stage('debug'){
	    steps {
  sh 'whoami'
  sh 'which docker || echo "docker not found"'
  sh 'docker version'
}

	}
        stage('Build Docker Image') {
            steps {
		dir("${APP_DIR}") {
                    	sh 'ls -l'
			sh 'docker build -t mini-node-app .'
            	}
	    }
        }
    }
}
