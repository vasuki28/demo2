pipeline {
    agent {label 'ubuntu'}

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
       stage('Create Directory') {
            steps {
                sudo 'mkdir -p mydir'
            }
        }

        stage('Create File') {
            steps {
                sudo 'echo "Hello from Jenkins!" > mydir/file.txt'
            }
        }

        stage('Copy Directory') {
            steps {
                sudo 'mkdir -p backup && cp -r mydir backup/'
            }
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
    }
}
