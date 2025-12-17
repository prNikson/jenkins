pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Подготовка окружения') {
            steps {
                ansiblePlaybook(
                    credentialsId: 'ssh-key',
                    playbook: 'ansible/playbooks/first-playbook.yml',
                    inventory: 'ansible/inventory/hosts',
                    extras: '-t install_docker clone_repos'
                )
            }
        }
        stage('Запуск приложений') {
            steps {
                ansiblePlaybook(
                    credentialsId: 'ssh-key',
                    playbook: 'ansible/playbooks/first-playbook.yml',
                    inventory: 'ansible/inventory/hosts',
                    extras: '-t start stop'
                )
            }
        }
    }
}
