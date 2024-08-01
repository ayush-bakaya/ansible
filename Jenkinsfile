pipeline {
    agent any
    
    stages {
        stage("SCM checkout") {
            steps {
                 git branch: 'main', url: 'https://github.com/ayush-bakaya/ansible.git'
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
