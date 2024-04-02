pipeline {
    agent any
    description 'Проект на С++ выводящий в консоль Hello World'
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    def compiler = 'g++'
                    sh "${compiler} main.cpp -o main"
                }
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts 'main'
            }
        }
    }

    post {
        success {
            echo 'Build successful. Artifacts are ready.'
        }
        failure {
            echo 'Build failed. Please check the build logs for details.'
        }
    }
}
