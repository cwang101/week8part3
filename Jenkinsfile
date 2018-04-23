#!groovy
pipeline {
    agent any
    tools {
        gradle 'Gradle 4.7'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                checkout scm
               sh 'gradlew build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                /* `make check` returns non-zero on test failures,
                 *  using `true` to allow the Pipeline to continue nonetheless
                 */
                sh 'gradlew test'
                junit 'reports/**/*.xml'
            }
        }
    }
}