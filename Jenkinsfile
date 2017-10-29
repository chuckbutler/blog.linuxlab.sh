node {
    checkout scm

    stage('Build Site') {
        _sh "docker run -ti -v $PWD:/site gcr.io/personal-1332/hugo"
    }
    stage('Publish'){
        _sh "gsutil rsync -R public gs://blog.linuxlab.sh"
    }
}
