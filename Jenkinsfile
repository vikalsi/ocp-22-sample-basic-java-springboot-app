pipeline {
    agent {
        label "java11"
    }
    stages {
        stage('SCM') {
            steps {
                echo 'Cloning the Code Repository..'
                git branch: 'main', url: 'https://github.com/bobbybabu007/ocp-22-sample-basic-java-springboot-app.git'
            }
        }
        stage('Compile') {
            steps {
                echo 'Compiling..'
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                sh 'mvn package'
            }
        }
                stage('Archiving') {
            steps {
                echo 'Archiving JAR File....'
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}
