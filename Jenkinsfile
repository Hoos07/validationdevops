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
        stage('build') {
                steps {
                    script {
                        sh 'ansible-playbook ansible/build.yml -i ansible/inventory/host.yml '
                    }
                }
        }
        }
}
