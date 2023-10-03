pipeline {
    agent {
        label 'Ansible'
    }
    stages {
        stage('Playbook') {
            steps {
                sh 'ansible-playbook -i inventory configuration_management.yml'
            }
        }
        stage ('Standard Mail') {
            steps {
                mail bcc: '', body: 'This is the system generated mail', cc: 'nirmalkumaran94@gmail.com', from: '', replyTo: '', subject: 'Playbook Initiated mail', to: 'nirmalniran0@gmail.com'
            }
        }
        stage ('Mail Extension') {
            steps {
                emailext attachLog: true, body: 'System generated Body', subject: 'System generated Subject', to: 'nirmalniran0@gmail.com'
            }
        }
        stage ('Clean WS') {
            steps {
                cleanWs()
            }
        }

    }
}
