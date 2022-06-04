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
                        sh 'npm install'
                        sh 'ansible-playbook ansible/build.yml -i ansible/inventory/host.yml '
                    }
                }
        }
        stage ('docker') {
                steps {
                    sh 'ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml'
                }
        }
        stage ('push to docker registry') {
                steps {
                    sh 'ansible-playbook ansible/docker-registry.yml -i ansible/inventory/host.yml'
                }
        }
        }
}
