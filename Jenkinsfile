pipeline {
  agent any
  stages {
    stage('SCM Checkout') {
      steps {
        git(branch: 'main', url: 'https://github.com/Eebru-gzy/ansible-config-mgt')
      }
    }
    stage('Set ansible config file') {
      steps {
        sh 'export ANSIBLE_CONFIG=~/ansible.cfg'
      }
    }
    stage('Execute Ansible') {
      steps {
        ansiblePlaybook colorized: true, credentialsId: 'real-mKey', disableHostKeyChecking: true, installation: 'my_ansible', inventory: 'inventory/dev', playbook: 'playbooks/site.yml'
      }
    }
    stage('Clean up') {
      steps {
        cleanWs(cleanWhenAborted: true, cleanWhenFailure: true, cleanWhenNotBuilt: true, cleanWhenUnstable: true, deleteDirs: true)
      }
    }
  }
}
