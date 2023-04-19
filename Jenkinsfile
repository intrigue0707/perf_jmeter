pipeline {
  agent any
  stages{
 stage('run test'){
   steps{
 sh "mkdir /tmp/reporting"
 sh "cd C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/workspace/jmeter/apache-jmeter-5.5/bin"
      sh  "-n -t ../Shophizer.jmx -l /tmp/reporting/Shophizer.jtl -e -o /tmp/reporting/HtmlReport"
   }}
 stage('publish results'){
   steps{
 sh "mv /tmp/reporting/* $WORKSPACE/$BUILD_NUMBER/"
     archiveArtifacts artifacts: '$WORKSPACE/$BUILD_NUMBER/Shophizer.jtl, $WORKSPACE/$BUILD_NUMBER/HtmlReport/index.html'
   }
    } 
  }
}
