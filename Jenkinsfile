pipeline {
    agent any

    stages {
        stage('Stage 0') {
            steps {
                sh "echo 'test-1' > scan.sarif"
                sh "echo 'test-2' > scan.sarif.json"
                sh "echo 'test-3' > scan.notsarif"
                archiveArtifacts artifacts:"scan*"
                registerBuildArtifactMetadata(name:"artifact1", url:"https://bla", version:"1", type:"mock", digest:"0123456789abcdef", label:"test-artifact");
                echo 'Done with stage 0!'
            }
        }
        stage('Stage 1') {
            steps {
                echo 'Not Waiting a bit'
                registerBuildArtifactMetadata(name:"artifact2", url:"https://bla/second", version:"1.1", type:"docker", digest:"0123456789abcdef", label:"test-artifact, second-try");
                echo 'Done with stage 1'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'Waiting a bit'
                sh "sleep 5"
                echo 'Done with stage 2'
            }
        }
    }
}
