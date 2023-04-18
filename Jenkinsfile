pipeline {
 stage('clone git repo'){
 git 'https://github.com/intrigue0707/perf_jmeter.git'
 }
 stage("configure") {
        sh "mkdir $WORKSPACE/$BUILD_NUMBER/"
    }
 stage('run test'){
 sh "mkdir /tmp/reports"
 sh "cd C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/workspace/jmeter/apache-jmeter-5.5/bin"
      sh "jmeter -Jjmeter.save.saveservice.output_format=xml
         -n -t C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/workspace/jmeter/apache-jmeter-5.5/bin/Shophizer.jmx
            -l /tmp/reports/JMeter.jtl -e -o /tmp/reports/HtmlReport"
 }
  stage('publish results'){

 sh "mv /tmp/reports/* $WORKSPACE/$BUILD_NUMBER/"

 archiveArtifacts artifacts: '$WORKSPACE/$BUILD_NUMBER/JMeter.jtl, $WORKSPACE/$BUILD_NUMBER/HtmlReport/index.html'
    } 
  }
}
