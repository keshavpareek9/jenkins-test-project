pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/keshavpareek9/jenkins-test-project.git'
      }
    }
    stage('Build') {
      steps {
        echo 'Building project...'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing project...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying project...'
        // Create index.html
        sh '''
          cat > index.html <<'HTML'
          <!DOCTYPE html>
          <html>
          <head>
            <title>Hello Jenkins</title>
          </head>
          <body>
            <h1>Hello from Jenkins!</h1>
            <p>This HTML page was generated during the pipeline.</p>
          </body>
          </html>
          HTML
        '''
      }
    }
    stage('Archive HTML') {
      steps {
        // Save the file as an artifact so you can download/view it
        archiveArtifacts artifacts: 'index.html', fingerprint: true
      }
    }
  }
}
