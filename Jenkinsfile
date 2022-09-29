pipeline {
    agent any

    tools {
        maven "M3"
    }
    stages {
        stage('Build Maven') {
            steps {
                println 'Cloning git repository...'
                git 'https://github.com/NW90/devopscon.git'
                println 'Starting the build...'
		sh "mvn clean install -Pci"
            }
            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
    }
}
