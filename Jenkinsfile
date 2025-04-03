pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven 'M398'
    }

    stages {
        stage('Build') {
            steps {
                // Run Maven on a Unix agent.
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Echo version') {
            steps {
                sh 'echo mvn -version'
            }
        }

        stage('Echo Hello World') {
            steps {
                sh 'echo Hello World'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'echo Deploying....'
            }
        }
    }
}
