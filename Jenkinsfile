properties([
                parameters([
                        string(name: 'one', defaultValue: ''),
                        string(name: 'second', defaultValue: ''),
                        string(name: 'third', defaultValue: ''),
                ])
        ])

pipeline {

    agent any
  
    
    stages {

        stage('unit-test') {
            steps {
                bat(/mvn -Dthrow=false -fn clean test/)
            }
        }
    }

    post {
            always {
                echo 'I will always say Hello again!'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }

}
