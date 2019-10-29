pipeline {
	agent any

	options {
		buildDiscarder(logRotator(numToKeepStr: '10'))
	}

	stages {
        stage('Build') {
            steps {
		cmakeBuild buildDir: 'build', buildType: 'Debug', cleanBuild: true, generator: 'Unix Makefiles', installation: 'InSearchPath', sourceDir: 'src'
            }
        }
	}
}
