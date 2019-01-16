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
                            rosdep update

                            ls -a

                            mkdir -p catkin_ws/src
                            ln -s `realpath dynamic_stack_decider` catkin_ws/src/
                            ln -s `realpath dynamic_stack_decider_visualisation` catkin_ws/src/
                            catkin init catkin_ws
                        '''
                    }
                }

                stage('Build package') {
                    steps {
                        sh '''
                            cd catkin_ws
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
