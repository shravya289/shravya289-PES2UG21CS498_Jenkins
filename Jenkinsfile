pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o your_executable_name your_cpp_file.cpp'
                }
            }
            post {
                always {
                    script {
                        if (currentBuild.result == 'FAILURE') {
                            echo 'pipeline failed'
                        }
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './your_executable_name'
                }
            }
            post {
                always {
                    script {
                        if (currentBuild.result == 'FAILURE') {
                            echo 'pipeline failed'
                        }
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                // Add your deployment steps here
            }
            post {
                always {
                    script {
                        if (currentBuild.result == 'FAILURE') {
                            echo 'pipeline failed'
                        }
                    }
                }
            }
        }
    }
}
