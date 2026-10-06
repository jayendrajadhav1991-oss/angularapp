pipeline {
    agent any
    tools { 
        nodejs "nodejs"
        }
    stages {
        stage("Checkout") {
            steps {
                    checkout scm
            }
        }
        stage("install packages") {
            steps {
                bat "npm ci"
            } 

        }
        stage("test") {
            steps{
                bat "npx ng text --no-watch --no-progress --browser=Chromeheadless"
                echo "testing"
            }
        }
        stage("Build") {
            steps {
                 bat "npx ng build --configuration production"
            }
        }

    }
    post {
        success {
            echo "Angular application build succesfully"
        } 
        failure {
            echo "angular build fail"
       }
    } 
    
}

