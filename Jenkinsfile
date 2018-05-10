#!groovy
node{
    def gradleHome = tool 'Gradle 4.7'
    env.PATH = "${gradleHome}/bin:${env.PATH}"

}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                checkout scm
                sh 'gradle build --info'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                /* `make check` returns non-zero on test failures,
                 *  using `true` to allow the Pipeline to continue nonetheless
                 */
                sh 'gradle test --info'
            }
        }
    }
}