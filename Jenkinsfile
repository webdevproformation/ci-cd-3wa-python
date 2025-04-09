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
                    python -m venv venv
                    ./venv/Scripts/activate
                    pip install Flask
                    python3 index.py
                    echo 'fin'
                    ls -al
                '''
            }
        }
    }
}