pipeline {
    agent any
    
    stages {
        stage('Cloning git') {
            steps {
                echo 'Cloning'
                //git 'https://github.com/lorelyn-bentazal/Test-Local.git'
            }
        }
        stage('Install dependencies') {
            steps {
                echo 'Installing'
                //sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Testing'
            }
        }
         stage('Sonar Scan') {
            steps {
                script {
                scannerHome = tool 'SonarScanner'
                }
                withSonarQubeEnv('sonarqube') {
                sh "${scannerHome}/bin/sonar-scanner \
                -Dsonar.projectKey=Jenkins"
                }
            }
        }
        stage('Deploy') {
            steps{
                echo 'Deployingy'
                //s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'lanzbucket', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: true, selectedRegion: 'ap-southeast-1', showDirectlyInBrowser: false, sourceFile: 'build/', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'jenkins-s3', userMetadata: [
            }
        }
    }
}
