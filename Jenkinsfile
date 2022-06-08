pipeline {
    agent none
    stages {
        stage('Non-Parallel Stage'){
            agent any
            steps {
                echo 'This stage will be executed first'
            }
        }
        stage('Run Tests') {
            parallel {
                stage('Test on Windows'){
                    agent {
                        label 'windows_node'
                    }
                    steps {
                        echo 'Task 1 on Agent'
                    }
                }
                stage("Test on master"){
                    agent any
                    steps {
                        echo 'Task 1 on Master'
                    }
                }
            }
        }
    }
}
