pipeline {
    agent any
    environment{
        NAME = 'Cafe'
    }

    stages {
        stage('Welcome') {
            steps {
                echo "Welcome to ${env.NAME}"
            }
        }
        stage('Software Versions') {
            steps {
                sh 'mvn --version'
                sh 'git --version'
                sh 'docker --version'
            }
        }
    }
    post {
        success {
            echo 'Triggering another project'
            build job: "env-variables-pipeline"
        }
    }
}
