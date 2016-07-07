node {
	stage 'Checkout'

		git url: 'https://github.com/tmoreira2020/jenkins-2-pipeline-test.git'

	stage 'Clean'

		mvn('clean')

	stage 'Build'

		mvn('compile')

	stage 'Checkstyle'

		mvn('checkstyle:check')

	stage 'Test - Unit'

		mvn('test')

	stage 'Package'

		mvn('package')

	stage 'Deploy'
	stage 'Test - Functional'
	stage 'Report'

	step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}

def mvn(args) {
	sh "${tool 'M3'}/bin/mvn ${args}"
}
