pipeline {
    agent any

    triggers{
        githubPush()
    }
    
    tools {
        jdk 'jdk_11_latest'
        gradle 'gradle_6_8_1'
    }

    environment {
        JAVA_HOME = "${tool 'jdk_11_latest'}"
        GRADLE_HOME = "${tool 'gradle_6_8_1'}"
    }

    stages {
        stage ('Test & Build JAR file') {
            steps {
                sh 'which java && gradle test && gradle clean build'
            }
        }
    }
}
