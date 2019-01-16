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
                stage('Install dependencies') {
                    steps {
                        sh '''#!/bin/bash
                            #source /catkin_ws/devel/setup.bash

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
                        sh '''#!/bin/bash
                            #source /catkin_ws/devel/setup.bash
                            #source /opt/ros/melodic/setup.bash
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
