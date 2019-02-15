pipeline {
  agent any
 
  options {
    copyArtifactPermission(projectNames: 'neutron*')
  }

  stages {
    stage('package') {
      steps {
        dir('dist') {
          deleteDir()
        }
        sh 'python setup.py sdist'
        sh 'find dist -type f -exec cp {} dist/neutron.tar.gz \\;'
        archiveArtifacts(artifacts: 'dist/neutron.tar.gz', onlyIfSuccessful: true)
      }
    }
  }
}

