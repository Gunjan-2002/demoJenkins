pipeline {
    agent any
    environment {
        name = 'Gunjan'
    }
    parameters {
        string(name: "person" , defaultValue: "Gunjan Nimbalkar" , description: "Who are you ?")
        booleanParam(name: "isMale" , defaultValue: "true" , description: "")
        choice(name: "City" , choices: ['Nagpur','Wardha','Amravati'] , description: "")
    }

    stages {
        stage('Running a multiple command') {
            steps {
                sh 'date'
                sh 'pwd'
            }
        }
        stage('Running multiple command as a single task') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
            }
        }
        stage('Environmenet Variable') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
            }
        }
        stage('Parameters') {
            steps {
                sh 'echo "${person}"'
            }
        }
        stage('Input: Continue ?') {
            input {
                message "Should we continue ?"
                ok "Yes, We should continue."
            }
            steps {
                sh 'echo "${person}"'
            }
        }
        stage('doc') {
            steps {
                sh 'echo "${person}"'
            }
        }
    }
    post {
        always {
            echo "I will say Hello always."
        }
        failure {
            echo "Failure"
        }
        success {
            echo "Success"
        }
    }
}
