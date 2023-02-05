pipeline{
    agent any
    environment {
        d_c=credentials("dockerpass")
    }
    stages{
        stage("git clone"){
            steps{
                checkout scm
            }
        }

        stage("building image"){
            steps{
                bat ("docker build -t sart22/image1 .") 
            }
        }
        
        stage("login"){
            steps{
                bat ("echo $d_c_PSW | docker login -u d_c_USR --password-stdin") 
            }
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
