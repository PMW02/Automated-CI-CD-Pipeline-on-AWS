pipeline {

    agent any

    environment {

        IMAGE_NAME = "pranav0202/automated-ci-cd-pipeline-on-aws"

        CONTAINER_NAME = "navneet-web"

    }

    stages {

        stage('Checkout') {

            steps {

                echo "Cloning Repository..."

                git branch: 'main',
                url: 'https://github.com/PMW02/Automated-CI-CD-Pipeline-on-AWS.git'

            }

        }

        stage('Build Docker Image') {

            steps {

                sh 'docker build -t $IMAGE_NAME:v1 .'

            }

        }

        stage('Push Docker Image') {

            steps {

                withCredentials([usernamePassword(

                    credentialsId: 'dockerhub-creds',

                    usernameVariable: 'DOCKER_USER',

                    passwordVariable: 'DOCKER_PASS'

                )]) {

                    sh '''

                    echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin

                    docker push $IMAGE_NAME:v1

                    '''

                }

            }

        }

        stage('Deploy Container') {

            steps {

                sh '''

                docker stop navneet-web || true

                docker rm navneet-web || true

                docker run -d \

                --name navneet-web \

                -p 80:80 \

                $IMAGE_NAME:v1

                '''

            }

        }

    }

}