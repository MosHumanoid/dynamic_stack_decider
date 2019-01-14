pipeline {
    agent {
        docker { image 'ros:melodic-ros-core' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo Hi'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Hallo Timon'
            }
        }

    }
}
