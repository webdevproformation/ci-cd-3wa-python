pipeline {
    agent any
    stages {
        stage('build') {
            agent {
                docker {
                    image 'malikh551/python_with_flask'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo 'exécution du projet'
                    python3 index.py
                    echo 'fin'
                    ls -al
                '''
            }
        }
    }
}