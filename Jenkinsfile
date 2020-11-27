@Library('piper-lib-os') _
node() {
       stage('prepare') {
        echo "starting stage prepare"
        checkout scm
        echo "checkout scm successful"
        fioriOnCloudPlatformPipeline script:this
       // fioriOnCloudPlatformPipeline(script: this, customDefaults: '.pipeline/config.yml')
        echo "end of stage prepare"
    }
 /* 
    stage('build') {
        echo "starting stage build"
        mtaBuild script: this
        echo "end of stage build"
    }
    stage('deploy') {
        echo "starting stage deploy"
        cloudFoundryDeploy script: this              
        echo "end of stage deploy"
    }*/
       
     stage('sonarScanner') {
        echo "starting SonarQube"
        sonarExecuteScan script: this
        echo "end of sonarQube"
    } 
       
     stage('tmsUpload') {
        echo "starting tms Upload"
        tmsUpload script: this
        echo "end of tms upload"
    }
}
