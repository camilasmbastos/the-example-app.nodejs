properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', 
                                      artifactNumToKeepStr: '', 
                                      daysToKeepStr: '', 
                                      numToKeepStr: '5'))

timestamps {
    node() {
        stage ('Checkout') {
            git 'https://github.com/camilasmbastos/PipelineScript'
            extcode = load 'deploy.groovy'
        }
        extcode.buildStage()
        extcode.testStage()
        extcode.archiveStage()
        extcode.deployHMGStage()
        extcode.releaseStage()
        extcode.deployPRDStage()
    }
}
