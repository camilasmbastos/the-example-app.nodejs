properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', 
                                      artifactNumToKeepStr: '', 
                                      daysToKeepStr: '', 
                                      numToKeepStr: '5')), 
            pipelineTriggers([bitbucketPush()])])
            
timestamps {
    node() {
        git 'https://github.com/camilasmbastos/PipelineScript'
        extcode = load 'deploy.groovy'
        
        extcode.developmentStages()
        
    }
}
