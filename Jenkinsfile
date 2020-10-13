pipeline {
    agent any
    environment {
        PATH = "C:\\Users\\Talha\\.crc\\bin\\oc;C:\\WINDOWS\\SYSTEM32"
    }
    stages {
        stage('build') {
            steps {
                script {
                    String login = "oc login -u talha.ahmed-northbaysolutions.ne -p Shooting#123 --insecure-skip-tls-verify https://api.shared-na4.na4.openshift.opentlc.com:6443 "
					bat(returnStdout: true , script: login)
					String projects = "oc get projects"
					def projectOut = bat(returnStdout: true , script: projects)
					if (projectOut.contains("template-test")) { 
                        String deleteProj = "oc delete project template-test"
                        def delOutput = bat(returnStdout: true , script: deleteProj)
                        print delOutput
                        sleep 5
                        String createProj = "oc new-project template-test"
                        def createOutput = bat(returnStdout: true , script: createProj) 
                        print createOutput
                    } 
                    else { 
                        String createProj = "oc new-project template-test"
                        def createOutput = bat(returnStdout: true , script: createProj) 
                        print createOutput
                    } 
                    
                    String createDB = "oc process -f .\\nuces-db.yaml --param-file=nuces-db-params.env | oc create -f -"
                    bat(returnStdout: true , script: createDB)
                    String createBackend = "oc process -f .\\nuces-backend.yaml --param-file=nuces-backend-params.env | oc create -f -"
                    bat(returnStdout: true , script: createBackend)
					String createFrontend = "oc process -f .\\nuces-frontend.yaml --param-file=nuces-frontend-params.env | oc create -f -"
					bat(returnStdout: true , script: createFrontend)
                }
            }
        }
    }
}