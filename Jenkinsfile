pipeline {
	agent any

	options {
		buildDiscarder(logRotator(numToKeepStr: '10'))
	}

	stages {
        stage('Build') {
            steps {
                cmake arguments: '-DCMAKE_TOOLCHAIN_FILE=~:wq/Projects/vcpkg/scripts/buildsystems/vcpkg.cmake', installation: 'InSearchPath'
                cmakeBuild buildType: 'Release', cleanBuild: true, installation: 'InSearchPath', steps: [[withCmake: true]]
            }
        }
	}
}
