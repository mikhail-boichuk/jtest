node('LR_NODE') {

def workspace
def globalScPath
def sc1Path
def sc2Path

stage('Checkout test sources'){
    	checkout scm
		workspace = pwd()
		globalScPath = pwd()
		sc1Path = globalScPath + "\\Jenkins_scenario1.lrs"
		sc2Path = globalScPath + "\\Jenkins_scenario2.lrs"
		echo workspace
}

stage('PerfTest_Scenario1') {
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '2500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: sc1Path
}

stage('PerfTest_Scenario2') {
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '1500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: sc2Path
}
}