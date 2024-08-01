pipeline {
    agent any
    
    stages {
        stage("SCM checkout") {
            steps {
                // Checkout the repository
                git branch: 'main', url: 'https://github.com/ayush-bakaya/ansible.git'
            }
        }
        
        stage("Execute Ansible") {
            steps {
                // Execute Ansible playbook
                ansiblePlaybook(
                    credentialsId: 'ansible', 
                    disableHostKeyChecking: true,
                    installation: 'Ansible',
                    inventory: 'dev.inv',
                    playbook: 'apache.yaml'
                )
            }    
        }    
    }
}
