pipeline {
  agent any
  stages{
 stage('run test'){
   steps{
 sh "mkdir /tmp/report"
 sh "cd C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/workspace/jmeter/apache-jmeter-5.5/bin"
      sh "jmeter.save.saveservice.output_format=xml -n -t ../Shophizer.jmx -l /tmp/reports/Shophizer.jtl -e -o /tmp/reports/HtmlReport"
   }}
 stage('publish results'){
   steps{
 sh "mv /tmp/reports/* $WORKSPACE/$BUILD_NUMBER/"
     archiveArtifacts artifacts: '$WORKSPACE/$BUILD_NUMBER/Shophizer.jtl, $WORKSPACE/$BUILD_NUMBER/HtmlReport/index.html'
   }
    } 
  }
}
