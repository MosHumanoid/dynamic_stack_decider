pipeline {
    agent {
        docker { image 'bitbots:base' }
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
                            mkdir -p catkin_ws/src catkin_ws/logs catkin_ws/build catkin_ws/devel
                            ln -s `realpath dynamic_stack_decider` catkin_ws/src/
                            ln -s `realpath dynamic_stack_decider_visualization` catkin_ws/src/
                            catkin init -w catkin_ws
                            cd catkin_ws

                            # source catkin_ws/devel/setup.bash
                            catkin list
                            rosdep update
                        '''
                    }
                }

                stage('Build package') {
                    steps {
                        sh '''
                            # cd catkin_ws
                            catkin list
                            ls
                            pwd
                            ls src
                            ls src/dynamic_stack_decider
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
