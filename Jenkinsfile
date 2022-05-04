pipeline {
    agent any
    
    environment {
        BLACKDUCK_URL="BD_URL%"
        BLACKDUCK_TOKEN="%BD_TOKEN%"
    }
    stages {   
        stage('Download dependencies') {
            steps {
                bat 'go mod download'            
            }
        }
        
        stage('Build code') {
            steps {
                bat 'go build'             
            }
        }
        
        stage('Análise Black Duck') {
            steps {
                synopsys_detect detectProperties: '--detect.blackduck.signature.scanner.snippet.matching=SNIPPET_MATCHING --detect.policy.check.fail.on.severities=BLOCKER', downloadStrategyOverride: [$class: 'ScriptOrJarDownloadStrategy']
            }
        }        
    }
}
