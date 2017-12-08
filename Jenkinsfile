pipeline {
    agent any

    stages {
        stage ('Say Hello from Shared library') {
        agent any
            steps {
            sayHello 'Awesome SVETLANA'
            }
         }
        stage ('Git information') {
        agent any
            steps {
                echo "My Branch Name: &{env.BRANCH_NAME}"
                script {
                def myLib = new mylinuxacademy.git.gitStuff();
                    echo "my Commit: ${myLib.gitCommit("${env.WORKSPACE}/.git")}"
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
