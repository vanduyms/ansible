pipeline {
    agent {
        docker {
            image 'willhallonline/ansible'
            args '-u root'
        }
    }
    stages {
        stage('Copy .env file') {
            steps {
                sh """
                scp vanduyms@Ubuntu:/home/vanduyms/.env /root/.env
                """
            }
        }

        stage('Run ansible') {
            steps {
                sh 'ansible-playbook -i ansible/inventory.ini ansible/deploy.yml'
            }
        }
    }
}
