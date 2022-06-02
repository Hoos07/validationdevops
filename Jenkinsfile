pipeline {
    agent any
        stages {
            stage('Pull') {
                steps {
                    script {
                        checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                            userRemoteConfigs: [[
                                credentialsId:'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',
                                url: 'https://github.com/hoos07'
                            ]]])
                    }
                }
            }
        }
}
