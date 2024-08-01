pipeline {
    agent any
    
    stages {
        stage("SCM checkout") {
            steps {
                git "https://github.com/ayush-bakaya/ansible.git"
            }
        }
        
        stage("Execute Ansible") {
            steps {
                ansiblePlaybook credentialsId: 'private-key',
                                 disableHostKeyChecking: true,
                                 installation: 'Ansible',
                                 inventory: 'dev.inv',
                                 playbook: 'apache.yml'
            }    
        }    
    }
}
