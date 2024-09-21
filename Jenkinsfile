pipeline {
  agent any
  
  triggers {
    githubPush()
  }
  
  stages {
    stage('Checkout') {
      steps {
        // Checkout the repository
        checkout scm
      }
    }

    stage('Make Changes') {
      steps {
        script {
          // Make any necessary changes (example: modifying a file)
          sh 'echo "New changes" >> file.txt'
        }
      }
    }

    stage('Commit and Push Changes') {
      steps {
        script {
          // Configure git user details (if needed)
          sh 'git config user.name "Your Name"'
          sh 'git config user.email "your.email@example.com"'

          // Stage, commit, and push the changes
          sh 'git add .'
          sh 'git commit -m "Automated commit for new changes"'
          sh 'git push origin HEAD'
        }
      }
    }
  }
}
