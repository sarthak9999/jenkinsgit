node
{
checkout scm
def imagename='image1'
stage("building docker image"){
    bat ("docker build -t ${imagename} .") 
}

stage("push image to docker hub"){
    withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerpwd')]) {
    bat ('docker login -u sart22 -p ${dockerpwd}')
}
    bat ('docker push ${imagename}} ')
}
}
