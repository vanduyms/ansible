pipeline {
    agent {
        docker {
            image 'willhallonline/ansible'
            args '-u root -v /home/vanduyms/.env:/ansible/.env'
        }
    }
    stage('Install Node.js') {
            steps {
                sh '''
                    apt-get update
                    apt-get install -y nodejs
                '''
            }
        }
    stages {
        stage('Run ansible') {
            steps {
                sh 'ansible-playbook -i ansible/inventory.ini ansible/deploy.yml'
            }
        }
    }
}
