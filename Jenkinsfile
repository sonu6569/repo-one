pipeline {
  agent {
  node {

        label "built-in"
}
}

 stages {
 stage ("clone") {

steps {
    sh "cd /root/23QA1"
    sh "rm -rf *"
    sh "git clone https://github.com/sonu6569/repo-one.git -b 23QA1"
    sh "aws s3 cp /root/23QA1 s3://sonubucket6569/23QA1 --recursive"
    
    sh "cd /root/23QA2"
    sh "rm -rf *"
    sh "git clone https://github.com/sonu6569/repo-one.git -b 23QA2"
    sh "aws s3 cp /root/23QA2 s3://sonubucket6569/23QA2 --recursive"

    sh "cd /root/23QA3"
    sh "rm -rf *"
    sh "git clone https://github.com/sonu6569/repo-one.git -b 23QA3"
    sh "aws s3 cp /root/23QA3 s3://sonubucket6569/23QA3 --recursive" 
}
}
 stage ("deployment-master") {
 steps {
     sh "aws s3 cp s3://sonubucket6569/23QA1 /mnt --recursive"
     sh "docker stop pramod"
     sh "docker rm pramod"
     sh "sudo docker run -itd -p 80:80 --name pramod httpd "
     sh "sudo docker cp /mnt/index.html pramod:/usr/local/apache2/htdocs"
}
}
}
}
