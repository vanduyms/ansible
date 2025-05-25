pipeline {
    agent {
        docker {
            image 'willhallonline/ansible'
            args '-u root -v /home/vanduyms/.env:/ansible/.env'
        }
    }
    stages {
        stage('Install Node.js') {
            steps {
                sh '''
                    apk update
                    apk add nodejs npm
                '''
            }
        }
        stage('Run ansible') {
            steps {
                sh 'ansible-playbook -i ansible/inventory.ini ansible/deploy.yml'
            }
        }
    }
}
