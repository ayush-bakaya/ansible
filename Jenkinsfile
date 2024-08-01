pipeline {
    agent any

    environment {
        ANSIBLE_SSH_PASS = credentials('ssh')
        ANSIBLE_BECOME_PASS = credentials('ssh')
    }
    stages {
        stage("SCM checkout") {
            steps {
                git branch: 'main', url: 'https://github.com/ayush-bakaya/ansible.git'
            }
        }
        
        stage("Execute Ansible") {
            steps {
                ansiblePlaybook(
                    credentialsId: 'private-key',
                    disableHostKeyChecking: true,
                    installation: 'Ansible',
                    inventory: 'dev.inv',
                    playbook: 'apache.yaml',
                    extraVars: [
                        ansible_ssh_pass: "${ANSIBLE_SSH_PASS}",
                        ansible_become_pass: "${ANSIBLE_BECOME_PASS}"
                    ]
                )
            }    
        }    
    }
}
