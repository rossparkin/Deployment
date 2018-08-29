pipeline {
  agent any
  stages {
    stage('Packer') {
      steps {
        powershell 'packer.exe -var-file="c:\\packer\\pso\\dse-vars.json" "c:\\packer\\pso.json"'
      }
    }
    stage('Terraform') {
      steps {
        powershell(script: 'Write-Output "Terraform"', returnStdout: true)
      }
    }
  }
  environment {
    Path = '%Path%;C:\\Packer;'
  }
}