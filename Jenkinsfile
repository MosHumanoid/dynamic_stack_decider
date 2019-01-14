pipeline {
    agent {
        docker { image 'ros:melodic-ros-core' }
    }

    environment {
        HOME = '$WORKSPACE'
    }

    stages {
        stage('Build') {
            stages {
                stage('Prepare Workspace') {
                    steps {
                        sh '''
                            rosdep update

                            ls -a

                            apt update
                            apt install -y python-catkin-tools

                            mkdir -p catkin_ws/src
                            ln -s `realpath dynamic_stack_decider` catkin_ws/src/
                            ln -s `realpath dynamic_stack_decider_visualisation` catkin_ws/src/
                            catkin init
                        '''
                    }
                }

                stage('Build package') {
                    steps {
                        sh '''
                            rosdep check dynamic_stack_decider
                        '''
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
