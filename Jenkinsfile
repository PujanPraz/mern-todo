@Library("Shared") _

pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'This is cloning'
                script {
                    clone("https://github.com/PujanPraz/mern-todo.git", "main")
                }
            }
        }
        stage('Build') {
            steps {
                echo 'This is building the code'
                script {
                    build("pujanprajapati", "mern-todo-app:frontend", "latest")
                    build("pujanprajapati", "mern-todo-app:backend", "latest")
                }
            }
        }
        stage('push') {
            steps {
                echo 'This is pushing the code'
                script{
                    push("mern-todo-app:frontend", "latest")
                    push("mern-todo-app:backend", "latest")
                }
            }
        }
        
    }
}