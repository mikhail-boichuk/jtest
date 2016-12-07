stage('PerfTest_Scenario1') {
    node('LR_NODE') {
    loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '2500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: '''Jenkins_scenario1.lrs
'''
}
}
stage('Sleep_stage') {
   echo 'This is sleep stage!'
   sleep 15
}
stage('PerfTest_Scenario2') {
    node('LR_NODE') {
 loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '1500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: '''Jenkins_scenario2.lrs
'''
}
}