pipeline {
agent {
 node {
      label "slave-1"
}
}
 stages {
stage ("deployment-slave-1") {

 steps {
     sh "aws s3 cp s3://sonubucket6569/23QA2 /mnt --recursive"
      //sh "cd /var/run"
     //sh "chmod 777 docker.sock"
      sh "docker stop nilesh"
     sh "docker rm nilesh"
     sh "sudo docker run -itd -p 90:80 --name nilesh httpd"
     sh "sudo docker cp /mnt/index.html nilesh:/usr/local/apache2/htdocs"

}
}
