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
                        sh "npm install"
                        sh 'ansible-playbook ansible/build.yml -i ansible/inventory/host.yml '
                    }
                }
        }
        }
}
