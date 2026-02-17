pipeline {
    agent any

    tools {
        jdk 'Java8'
        maven 'Maven3'
    }

    options {
        timeout(time: 5, unit: 'MINUTES')
    }

    parameters {
        choice(
            name: 'MAVEN_COMMAND',
            choices: [
                'mvn clean install',
                'mvn jetty:run'
            ],
            description: 'Select Maven command'
        )
    }

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/sohailsd888/game-of-life.git',
                    branch: 'master'
            }
        }

        stage('Build') {
            steps {
                echo "maven_command: ${params.MAVEN_COMMAND}"
            }
        }
    }
}
