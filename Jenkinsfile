pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Cloning repository..."
                git branch: 'main', url: 'https://github.com/Harini-01912/week5'
            }
        }

        stage('Compile') {
            steps {
                echo "Compiling Java files..."
                bat 'javac Factorial.java TestFactorial.java'
            }
        }

        stage('Test') {
            steps {
                echo "Running Test..."
                bat 'java TestFactorial'
            }
        }
        stage('Run') {
    steps {
        echo "Running Java program..."
        bat 'java TestFactorial'
    }
}
        stage('Package JAR'){
            steps{
                echo "Build"
                bat 'jar cfm factorial.jar manifest.txt Factorial.class'
            }
        }
        stage('Archive JAR'){
            steps{
                echo "Deploy"
                archiveArtifacts artifacts:'factorial.jar'
            }
        }
            
    }

    post {
        success {
            echo 'Build,test,run and JAR creation Successful and artifact is ready!'
        }

        failure {
            echo 'Build Failed!'
        }
    }
}











