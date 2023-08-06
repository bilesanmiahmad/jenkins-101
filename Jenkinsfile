pipeline {
    agent {
        label 'python'
    }

    triggers {
        pollSCM '*/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "The node name for this pipeline is ${NODE_NAME}"
                cat /etc/os-release
                sudo apt update
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "The current workspace is ${WORKSPACE}"
                pwd
                cd myapp
                pwd
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "Delivering the awesome product for all to use..."
                '''
            }
        }
    }
}