pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Подготовка окружения') {
            steps {
                ansiblePlaybook(
                    playbook: 'ansible/playbooks/first-playbook.yml',
                    inventory: 'ansible/inventory/hosts',
                    extras: '--tags install_docker clone_repos'
                )
            }
        }
        stage('Запуск приложений') {
            steps {
                ansiblePlaybook(
                playbook: 'ansible/playbooks/first-playbook.yml',
                inventory: 'ansible/inventory/hosts'
                extras: '--tags start stop'
                )
            }
        }
    }
}
