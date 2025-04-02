pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven 'M398'
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'ch/jenkins-file-add', credentialsId: 'abb59ec2-0233-41d1-8ab5-8bf86232c6dc', url: 'https://github.com/IvyMurage/jenkins_file_hello_world'

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

        stage('Deploy') {
            steps {
                script {
                    for (int i = 0; i < 10; i++) {
                        echo "Deploying $i"
                    }
                }
                sh 'echo Deploying....'
            }
        }
    }
}
