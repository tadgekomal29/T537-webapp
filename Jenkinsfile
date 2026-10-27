pipeline{
    environment{
        IMAGE_NAME = 'webapp'
        IMAGE_TAG = '${Build_Number}'

    }
    stages{
        stage("Checkout"){
            steps{
                checkout scm
            }
        }
        stages{
            stage("Build"){
                steps{
                    sh '''
                    docker build -t ${IMAGE_NAME}:${IMAGE_TAG}
                    '''
            }
        }
         stages{
            stage("Deploy"){
                steps{
                    sh '''
                    docker run -d -p 80:80 ${IMAGE_NAME}:${IMAGE:TAG}
                    '''
            }
        }

    }
}