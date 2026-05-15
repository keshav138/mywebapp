pipeline{
    agent any

    stages{
        stage('Create the docker image'){
            steps{
                bat 'docker build -t mypage:v1-image .'
            }
        }

        stage('Run the container'){
            steps{
                bat 'docker rm -f mypage:v1-container || true'
                bat 'docker run -d -p 80:80 --name mypage:v1-container mypage:v1-image'
            }
        }
    }
}