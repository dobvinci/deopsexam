node {

stage('Clone Repository')
{
checkout scm
}

stage('Show me the files'){
sh "ls -l"
}

stage('Build docker image'){

sh "docker build -t docker_exam:latest ."
}

stage('Docker login to hub and push the image'){
sh "docker login -u 'dobvinci' -p 'Digital00*' "
sh "docker tag docker_test:latest dobvinci/docker_exam:latest"
sh "docker push dobvinci/docker_exam:latest"
}

stage('Apply changes to the environment') {
sh "ls -l"
docker run --name docker_exam:latest -p 1610 -v /var/run/docker.sock:/var/run/docker.sock dobvinci/docker_exam:latest
}


}
