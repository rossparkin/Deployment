pipeline {
  agent any
  stages {
    stage('Packer') {
      parallel {
        stage('Packer Interface') {
          steps {
            powershell 'packer.exe build -var-file="c:\\packer\\pso\\dse-vars.json" "c:\\packer\\pso.json"'
          }
        }
        stage('Packer DSE') {
          steps {
            powershell(script: 'Write-Output "Building DSE image"', returnStdout: true)
          }
        }
      }
    }
    stage('Terraform') {
      steps {
        powershell(script: 'Write-Output "Terraform"', returnStdout: true)
      }
    }
  }
}