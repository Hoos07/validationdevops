pipeline {
    agent any
        stages {
            stage('Pull') {
                steps {
                    script {
                        checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                            userRemoteConfigs: [[
                                credentialsId:'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',
                                url: 'https://github.com/hoos/07'
                            ]]])
                    }
                }
            }
        }
}
