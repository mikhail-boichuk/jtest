node('LR_NODE') {

def testData = pwd()+"\\testData"
def sc1Path = testData + "\\Jenkins_scenario1.lrs"
def sc2Path = testData + "\\Jenkins_scenario2.lrs"

stage('Checkout test data'){
    dir (testData) {
		checkout scm
		echo testData
	}
}

stage('PerfTest_Scenario1') {
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '2500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: sc1Path
}

stage('PerfTest_Scenario2') {
	loadRunnerTest archiveTestResultsMode: 'PUBLISH_HTML_REPORT', fsTimeout: '1500', ignoreErrorStrings: 'Error: CPU usage for this load generator has exceeded 80%', perScenarioTimeOut: '20', testPaths: sc2Path
}

stage('Cleanup environment') {
	dir (testData) {
	    deleteDir()
	}
}
}