node('LR_NODE') {

def testData
def sc1Path
def sc2Path

stage('Checkout test data'){
    dir (pwd()+"\\testData") {
		checkout scm
		testData = pwd()
		sc1Path = testData + "\\Jenkins_scenario1.lrs"
		sc2Path = testData + "\\Jenkins_scenario2.lrs"
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