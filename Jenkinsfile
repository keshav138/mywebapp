pipeline{
    agent any

    stages{
        stage('Create the docker image'){
            steps{
                bat 'docker build -t mypagev1-image .'
            }
        }

        stage('Run the container'){
            steps{
                bat 'docker rm -f mypagev1-container || true'
                bat 'docker run -d -p 80:80 --name mypagev1-container mypagev1-image'
            }
        }
    }
}