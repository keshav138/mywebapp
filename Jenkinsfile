pipeline{
    agent any

    stages{
        stage('Create the docker image'){
            steps{
                bat 'docker build -t nginx-image'
            }
        }

        stage('Run the container'){
            steps{
                bat 'docker stop -f nginx-container || true'
                bat 'docker run -p 80:80 --name nginx-container nginx-image'
            }
        }
    }
}