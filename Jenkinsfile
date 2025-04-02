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

            // To run Maven on a Windows agent, use
            // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

        // post {
        //     // If Maven was able to run the tests, even if some of the test
        //     // failed, record the test results and archive the jar file.
        //     success {
        //         junit '**/target/surefire-reports/TEST-*.xml'
        //         archiveArtifacts 'target/*.jar'
        //     }
        // }
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
                sh 'echo Deploying....'
                sleep 3
                echo 'This app has being deployed helooo'
            }
        }
    }
}
