pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    def crcOc = bat(returnStdout: true , script: "SET PATH=C:\\Users\\Talha\\.crc\\bin\\oc;%PATH%")
                    print crcOc
                    String login = "oc login -u talha.ahmed-northbaysolutions.ne -p Shooting#123 https://api.shared-na4.na4.openshift.opentlc.com:6443"
					def loginBat = bat(returnStdout: true , script: login)
					// print loginBat
                    // def dir = bat(returnStdout: true , script: "dir")
					// print dir
                }
            }
        }
    }
}