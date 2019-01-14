pipeline {
    agent {
        docker { image 'ros:melodic-ros-core' }
    }

    stages {
        stage('Build') {
            stages {
                stage('Nested Build') {
                    steps {
                        sh 'Hi'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                sh 'echo Hallo Timon'
            }
        }

    }
}
