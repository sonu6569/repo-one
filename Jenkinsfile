pipeline {
agent {
node {
 label "slave-2"

}
}

stages {
steps {
      sh "aws s3 cp s3://sonubucket6569/23QA3 /mnt --recursive"
       //sh "cd /var/run"
       //sh "chmod 777 docker.sock"
        sh "docker stop nagesh"
         sh "docker rm nagesh"
       sh "sudo docker run -itd -p 8081:80 --name nagesh httpd"
       sh "sudo docker cp /mnt/index.html nagesh:/usr/local/apache2/htdocs"
}
}
}
}


    
