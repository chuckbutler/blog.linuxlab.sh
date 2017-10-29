node {
    checkout scm

    stage('Build Site') {
      dir('bin'){
        sh "curl -L -O https://github.com/gohugoio/hugo/releases/download/v0.30.2/hugo_0.30.2_Linux-32bit.tar.gz"
        sh "tar xvfz hugo_0.30.2_Linux-32bit.tar.gz"
        sh "ls"
      }
      sh "./bin/hugo"
    }

    stage('Publish Site'){
        sh "gsutil rsync -R public gs://blog.linuxlab.sh"
    }
}
