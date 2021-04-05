@Library('piper-lib-os') _
node() {
    
    triggers {
        cron('H */4 * * 1-5')
    }
    
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    
    stage('build') {
        mtaBuild script: this
    }
    
    stage('deploy') {
        cloudFoundryDeploy script: this
    }

}
