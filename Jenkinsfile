pipeline {
    agent any

    stages {
        stage('Cloning Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/johnnynumberfive-coder/jk-public-gh.git'
            }
        }
        
        stage('Building Image') {
            steps {
                sh 'docker build -t webapp:${BUILD_NUMBER} .'
            }
        }
        
             stage('Running Container') {
            steps {
                sh 'docker run --rm -d -p 3000:3000 --name webapp_ctr webapp:${BUILD_NUMBER}\'\'\''
            }
        }
    }
    }
