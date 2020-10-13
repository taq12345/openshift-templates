pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    cmd = "oc login -u talha.ahmed-northbaysolutions.ne -p Shooting#123 https://api.shared-na4.na4.openshift.opentlc.com:6443"
					def output = bat(returnStdout: true , script: cmd)
					print output
                }
            }
        }
    }
}