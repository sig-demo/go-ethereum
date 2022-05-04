pipeline {
    agent any
    
    environment {
        BLACKDUCK_URL="BD_URL%"
        BLACKDUCK_TOKEN="%BD_TOKEN%"
    }


    stages {        
        stage('Análise Black Duck') {
            steps {
                synopsys_detect detectProperties: '', downloadStrategyOverride: [$class: 'ScriptOrJarDownloadStrategy']
            }
        }        
    }
}
