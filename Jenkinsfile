pipeline {
    agent any
    tools {
        maven '3.9.1'
    }
    parameters {

    // the first option is the default value even if you don't chose it.
        choice choices: ['one', 'two', 'three'], description: 'pick something', name: 'CHOICE'
    }
    stages {
        stage("build") {
            steps {
                echo 'building the application...'
                sh "echo choice: ${params.CHOICE}"
                script {
                    def test = 2 + 2 > 3 ? 'cool' : 'not cool'
                        echo test
                }
                sh "mvn clean install"

//                 sh './gradlew -v'
            }
        }
        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the application...'
            }
        }
    }
}