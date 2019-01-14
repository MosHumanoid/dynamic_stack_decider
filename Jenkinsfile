pipeline {
    agent {
        docker {
            args '-u 0:0'
            image 'ros:melodic-ros-core'
        }
    }

    stages {
        stage('Build') {
            stages {
                stage('Prepare Workspace') {
                    steps {
                        sh '''
                            rosdep update

                            mkdir -p catkin_ws/src
                            cd catkin_ws
                            catkin init
                        '''
                    }
                }

                stage('Build package') {
                    steps {
                        sh 'echo Hello'
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
