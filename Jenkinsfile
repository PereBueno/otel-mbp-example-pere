pipeline {
    agent any

    stages {
        stage('Stage 0') {
            steps {
                registerBuildArtifactMetadata(name:"artifact1", url:"https://bla", version:"1", type:"mock", digest:"0123456789abcdef", label:"test-artifact";)
                echo 'Done with stage 0!'
            }
        }
        stage('Stage 1') {
            steps {
                echo 'Waiting a bit'
                sh "sleep 10"
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
