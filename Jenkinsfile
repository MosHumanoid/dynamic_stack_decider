pipeline {
    agent {
        docker { image 'ros:melodic-ros-core' }
    }

    stages {
        stage('Build') {
            stages {
                stage('Prepare Workspace') {
                    steps {
                        sh 'Hi'
                    }
                }

                stage('Build package') {
                    steps {
                        sh 'Hello'
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
