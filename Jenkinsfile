pipeline{
    agent any
    environment {
        DOCKERHUB_CREDENTIALS= credentials("dockerpass")
    }
    stages{
        stage("git clone"){
            steps{
                checkout scm
            }
        }

        stage("building image"){
            steps{
                echo "$BUILD_NUMBER here--------"
                bat ("docker build -t sart22/image1 .") 
            }
        }
        
        stage("login"){
            steps{
                // attention on how to use quotes with $ sign 
                bat 'docker login -u %DOCKERHUB_CREDENTIALS_USR% -p %DOCKERHUB_CREDENTIALS_PSW%' 
            }
        }
        
        stage("push image to docker"){
            steps{
                bat 'docker push sart22/image1 ' 
            }
        }

    }
    post{
        always{
            bat 'docker logout'
        }
    }
}


// node
// {
// checkout scm

// environment{
//     DOCKERHUB_CREDENTIALS=credetilals("dockerpass")
// }
// stage("building docker image"){
//     bat ("docker build -t sart22/image1 .") 
// }

// stage("push image to docker hub"){
//     bat ("$DOCKERHUB_CREDENTIALS_USR")
//     // bat ('docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin')
//     // bat ('docker push sart22/image1 ')
// }
// }
