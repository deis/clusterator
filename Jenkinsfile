#!groovy

node('linux') {
 stage 'Checkout'
 checkout scm

 stage 'Docker Build and Push - Quay.io'
 def quayUsername = "deisci+jenkins"
 def quayEmail = "deis+jenkins@deis.com"
 withCredentials([[$class: 'StringBinding',
                    credentialsId: 'c67dc0a1-c8c4-4568-a73d-53ad8530ceeb',
                    variable: 'QUAY_PASSWORD']]) {

   sh """
     docker login -e="${quayEmail}" -u="${quayUsername}" -p="\${QUAY_PASSWORD}" quay.io
     make build docker-immutable-push
   """
 }
}
