properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', 
                                      artifactNumToKeepStr: '', 
                                      daysToKeepStr: '', 
                                      numToKeepStr: '5')), 
            pipelineTriggers([bitbucketPush()])])
            
timestamps {
    node() {
        git 'https://github.com/camilasmbastos/PipelineScript'
        extcode = load 'deploy.groovy'
        
        extcode.checkoutStage()
        extcode.buildStage()
        extcode.testStage()
        extcode.archiveStage()
        extcode.deployHMGStage()
        extcode.releaseStage()
        extcode.deployPRDStage()
        
    }
}
