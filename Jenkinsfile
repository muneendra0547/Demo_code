pipeline {
    agent any

    stages {
        stage('git_clone') {
            steps {
                sh '''
                echo 'cloning code from git'
                git clone 'https://github.com/muneendra0547/Demo_code.git'
                '''
            }
        }
        stage('BUILD') {
            steps {
                sh '''
                echo 'here compiling the dev code'
                pwd
                ls -ll
                mvn clean
                mvn compile
                '''
            }
        }
        stage('test') {
            steps {
                sh '''
                echo 'validating test cases'
                pwd
                ls -ll
                mvn test
                '''
            }
        }
      stage('sonar') {
            steps {
                sh '''
                echo 'validating sonar code coverage'
                pwd
                ls -ll
                mvn sonar:sonar
                '''
            }
        }
        stage('package') {
            steps {
                sh '''
                echo 'creating package'
                pwd
                ls -ll
                mvn package
                '''
            }
        }
        stage('jfrog') {
            steps {
            sh '''
            echo 'uploading packages to jfrog repo'
            '''
            }
        }
    }
}

