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

        stage('Testing-Stage'){
            steps{
                sh'''
                docker run -it -d -p 80:80 --name project1 ${IMAGE_NAME}
                '''
            }
        }
    }
}