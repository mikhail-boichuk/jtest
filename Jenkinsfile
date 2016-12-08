stage('PerfTest_Scenario1') {
    node('LR_NODE') {
	checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a9e7029d-9514-45e7-ac1a-7d82ded8d8c2', url: 'https://github.com/mikhail-boychuk/jtest.git']]])
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '2500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: 
pwd()+"\\Jenkins_scenario1.lrs"
}
}
stage('Sleep_stage') {
   echo 'This is sleep stage!'
   sleep 15
}
stage('PerfTest_Scenario2') {
    node('LR_NODE') {
	checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a9e7029d-9514-45e7-ac1a-7d82ded8d8c2', url: 'https://github.com/mikhail-boychuk/jtest.git']]])
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '1500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: 
pwd()+"\\Jenkins_scenario2.lrs"
}
}