pipeline {
    agent any
    stages {
        stage('build') {
            agent {
                docker {
                    image 'python'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo 'jenkins va installer les dépendances du projet'
                    pip install -r requirements.txt
                    python3 index.py
                    echo 'fin'
                    ls -al
                '''
            }
        }
    }
}