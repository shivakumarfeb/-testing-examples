pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Unit Tests') {
            steps {
                sh 'mvn surefire:test'
            }
        }
         stage('Integration Tests') {
            steps {
                sh 'mvn failsafe:integration-test'
            }
        }
    }
    post {
        always {
           // junit 'target/surefire-reports/TEST-*.xml'
           junit /var/lib/jenkins/workspace/maventest1/Report_TC_SmokeTests.xml
        }
        
    }
}
