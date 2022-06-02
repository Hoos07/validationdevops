pipeline {
    agent any
        stages {
            stage('Pull') {
                steps {
                    script {
                        checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                            userRemoteConfigs: [[
                                credentialsId:'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',
                                url: 'https://github.com/hoos07/validationdevops'
                            ]]])
                    }
                }
            }
        }
}
