pipeline {
    agent {
        docker {
            image 'willhallonline/ansible'
            args '-u root -v $HOME/.env:/home/.env'
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
