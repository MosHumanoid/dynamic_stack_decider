pipeline {
    agent {
        docker { image 'ros:melodic-ros-core' }
    }

    stages {

        stage('Build') {
            stage('Prepare workspace') {
                sh "
                    ls
                    pwd

                    rosdep init

                    mkdir -p catkin_ws/src
                    cd catkin_ws
                    catkin init

                    ls

                "
            }

            stage('Build package') {

            }

        }

        stage('Test') {
            steps {
                sh 'echo Hallo Timon'
            }
        }
    }
}
