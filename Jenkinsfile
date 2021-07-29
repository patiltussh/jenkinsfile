pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    ResultCode = sh (
                        returnStatus: true,
                        script: "node -versio"
                    )
                    currentBuild.result = "SUCCESS"
                    if ( ResultCode == 1 ) {
                      echo "ERROR: plan failed"
                      exit 1
                } // script {}
           }
        }
    }
}
}
