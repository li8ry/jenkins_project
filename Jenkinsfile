VERSION = 'all'

pipeline {
    agent { node { label 'slave01' } }
    triggers {
        cron('* * * * *')
    }
    parameters {
        choice(name: 'VERSION', choices: ['all', 'cCode', 'pythonCode', 'bashCode'], description: 'Chose code example to run')
//         booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
        stages {
        stage("cCode") {
            when {
                expression { 
                    params.VERSION == 'cCode' || params.VERSION == 'all'
                }
            }
            steps {
//                 g++ "./cScript.c"
                echo 'test'
            }
        }
        stage("pythonCode") {
            when {
                expression { 
                    params.VERSION == 'pythonCode' || params.VERSION == 'all'
                }
            }
            steps {
//                 script {
//                     gv.buildApp()
//                 }
                echo 'test'
            }
        }
        stage("bashCode") {
            when {
                expression { 
                    params.VERSION == 'bashCode' || params.VERSION == 'all'
                }
            }
            steps {
//                 sh "./bash.sh"
                echo 'test'
            }
        }
    }   
}
