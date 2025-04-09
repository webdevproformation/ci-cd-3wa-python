pipeline {
    agent any
    stages {
        stage("exemple"){
            parallel {
                stage("etape1 premier"){
                    steps{
                        sh "echo 'etape1'"
                    }
                }
                stage("etape1 en même temps"){
                    steps{
                        sh "echo 'travailler en parallèle'"
                    }
                }
            }
        }
        stage('build') {
            agent {
                docker {
                    image 'malikh551/python_with_flask:latest'
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