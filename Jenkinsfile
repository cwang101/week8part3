#!groovy
node (){
stage 'Build and Test'
env.PATH = "${tool 'M3'}/bin:${env.PATH}"
//checkout scm
git url:"https://github.com/cwang101/week8part3.git"
sh 'mvn clean package'
}