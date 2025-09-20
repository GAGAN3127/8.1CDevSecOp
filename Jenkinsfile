pipeline {
  agent any
  options { ansiColor('xterm'); timestamps() }
  triggers { pollSCM('H/5 * * * *') } // per brief: use polling, not webhook
  stages {
    stage('Build') { steps { echo 'Task: compile/package | Tool: Maven' } }
    stage('Unit & Integration Tests') { steps { echo 'Task: run tests | Tools: JUnit + Surefire/Failsafe' } }
    stage('Code Analysis') { steps { echo 'Task: static analysis | Tool: SonarQube/SonarCloud' } }
    stage('Security Scan') { steps { echo 'Task: dependency scan | Tool: npm audit or Snyk' } }
    stage('Deploy to Staging') { steps { echo 'Task: deploy artefact | Tool: Ansible/SSH' } }
    stage('Integration Tests on Staging') { steps { echo 'Task: smoke/API tests | Tool: Newman/Cypress' } }
    stage('Deploy to Production') { steps { echo 'Task: rolling deploy | Tool: Ansible/Helm' } }
  }
}
s
