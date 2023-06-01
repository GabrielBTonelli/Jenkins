pipeline {
    agent any
    stages {
        stage("Clean Up"){ // It's a good practice to setup a Clean Up STAGE on the begging, once Jenkins always create a new repo when start a work.
            steps {         // on this way you can clean the previous work and make sure your job will work properly
                deleteDir()
            }
        }
        stage("Clone Repo"){
            steps {
                sh "git clone https://github.com/jenkins-docs/simple-java-maven-app.git"
            }
        }
        stage("Build"){
            steps {
                dir("simple-java-maven-app") {
                    sh "mvn clean install"
                }
            }
        }
        stage("Test"){
            steps {
                dir("simple-java-maven-app") {
                    sh "mvn test"
                }
            }
        }
    }
}