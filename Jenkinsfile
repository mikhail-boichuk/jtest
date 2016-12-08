node('LR_NODE') {

def workspace

stage('Checkout test sources'){
    	checkout scm
		workspace = pwd()
		echo workspace
}

stage('PerfTest_Scenario1') {
	def scPath = workspace + "\\Jenkins_scenario1"
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '2500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: scPath
}

stage('PerfTest_Scenario2') {
	def scPath = workspace + "\\Jenkins_scenario2"
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '1500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: scPath
}
}