pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        pollSCM '* * * * *' // the SCM trigger will run ones every 5 min to update
    }                       // from the github repo
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Oussama
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}