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
        stage("install package") {
            steps {
                bat "npm ci"
            } 

        }
        stage("testing") {
            steps{
                bat "npx ng test --no-watch --no-progress --browser=ChromeHeadless"
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
        echo "angular application succesfully"
        
    } 
    failure {
        echo "angular build fail"
    }

}
}