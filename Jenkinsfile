pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = "false"
    }

    stages {
        stage('Ansible Stage') {
            steps {
                echo 'AnsiblePlaybook Deployment Started.'
                sh '''
                ansible-playbook -i localhost, -c local deploy.yml --become
                '''
            }
        }
    }

    post {
        failure {
            echo 'Deployment Failed.'
        }
        success {
            echo 'Deployment Successful.'
        }
    }
}
