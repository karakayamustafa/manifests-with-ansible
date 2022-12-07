pipeline {
    agent { label 'ansible' }

    environment {
        K8S_AUTH_KUBECONFIG = credentials('kubeconfig')
        REGCRED = credentials('regcred')
    }

    stages {
        stage('Clone repository') {
            steps {
                checkout scm
            }
        }

        stage('Apply playbook') {
            steps {
                ansiblePlaybook('deploy-playbook.yml') 
            }
        }
    }
}