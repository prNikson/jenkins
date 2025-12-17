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
                )
            }
        }
        stage('Запуск приложений') {
            steps {
                ansiblePlaybook(
                playbook: 'ansible/playbooks/first-playbook.yml',
                inventory: 'ansible/inventory/hosts'
                )
            }
        }
    }
}
