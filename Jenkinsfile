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
