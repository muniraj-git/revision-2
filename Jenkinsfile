pipeline{
    
    agent any

    environment{
        IMAGE_NAME = "munirajmurugesh/project1:${GIT_COMMIT}"
    }
    stages{
        stage('git-checkout'){
            steps{
                git url: 'https://github.com/muniraj-git/revision-2.git', branch: 'revision-2'
            }
        }

        stage('Build-Stage'){
            steps{
                sh'''
                     docker build -t $IMAGE_NAME .
                '''

            }
        }
    }
}