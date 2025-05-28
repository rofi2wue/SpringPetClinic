pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage("checkout") {
            steps {
                // Get some code from a GitHub repository
                git branch: "main", url: "https://github.com/rofi2wue/SpringPetClinic.git"
            }
        }
        stage("build") {
            steps {
                sh "mvn compile"
            }
        }
        stage("test") {
            steps {
                sh "mvn test"
            }
        }
        stage("package") {
            steps {
                sh "mvn package"
            }
        }
        stage("deploy") {
            steps {
                sh "java -jar /home/coder/.jenkins/workspace/petclinicDeclarativePipeline/target/*.jar"
            }
        }
    }
}
