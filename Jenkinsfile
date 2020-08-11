pipeline {

    agent any
    properties([
  parameters([
    string(name: 'submodule', defaultValue: ''),
    string(name: 'submodule_branch', defaultValue: ''),
    string(name: 'commit_sha', defaultValue: ''),
  ])
])
    
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
