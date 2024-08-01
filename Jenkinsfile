pipeline {
    agent any
    
    stages {
        stage("SCM checkout") {
            steps {
                git 'https://github.com/Sada-Siva-Reddt/blog1.git',branch:'main'
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
