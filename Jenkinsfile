pipeline {
    agent {
        docker { image 'bitbots:builder' }
    }

    environment {
        HOME = '$WORKSPACE'
    }

    stages {
        stage('Build') {
            stages {
                stage('Prepare Catkin Workspace') {
                    steps {
                        sh '''
                            . /catkin_ws/devel/setup.sh

                            ln -s `realpath dynamic_stack_decider` /catkin_ws/src/
                            ln -s `realpath dynamic_stack_decider_visualization` /catkin_ws/src/
                            cd /catkin_ws

                            rosdep update
                            rosdep install -ya
                        '''
                    }
                }

                stage('Build package') {
                    steps {
                        sh '''
                            env

                            cd /catkin_ws
                            catkin build

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
