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
    stage('Terraform DB') {
      steps {
        powershell(script: 'Write-Output "Terraform"', returnStdout: true)
      }
    }
    stage('Configure DB') {
      steps {
        powershell 'Write-Output "Hello"'
      }
    }
    stage('Terraform Compute') {
      steps {
        powershell 'Write-Output "Hello"'
      }
    }
  }
}