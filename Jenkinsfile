pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                git branch: 'main', credentialsId: 'GitHubCreds', url: 'https://github.com/NAGENDRASAICH/htmlfilerepo.git'
            }
        }

        stage('Build and Test') {
            steps {
                // Placeholder for build and test operations
                echo 'Build and Test successful!'
            }
        }

        stage('Generate Artifact') {
            steps {
                // Create the artifacts directory if it doesn't exist
                sh 'mkdir -p artifacts'
                // Copy the dev.html file to the artifacts directory
                sh 'cp dev.html ./artifacts/'
            }
        }
    }

    post {
        success {
            // Archive the generated artifact
            archiveArtifacts artifacts: 'artifacts/*.html', onlyIfSuccessful: true
            // Print a success message if the pipeline completes successfully
            echo 'Pipeline completed successfully!'
        }
    }
}
