pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          node {
            def dep = vraDeployFromCatalog(
              catalogItemName: 'verinttestl1stest',
              count: 1,
              deploymentName: 'JenkinsProgrammatic-#',
              projectName: 'arun',
              reason: 'Test',
              timeout: 300,
              version: '2')
              assert dep != null

              // Get the address
              def addr = vraWaitForAddress(
                deploymentId: dep[0].id,
                resourceName: 'UbuntuMachine')
                echo "Deployed: $dep[0].id, addresses: ${addr[0]}"
              }
            }

          }
        }

      }
      environment {
        vraUrl = 'vra.cap.org'
        username = 'arun'
        password = 'VMware123!'
        domain = 'cap.org'
      }
    }