VERSION = 'none'

pipeline {
    agent { node { label 'slave01' } }
    triggers {
        cron('* * * * *')
    }
    parameters {
        choice(name: 'VERSION', choices: ['cCode', 'pythonCode', 'bashCode'], description: '')
//         booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("cron") {
//             when {
//                 triggeredBy "TimerTrigger"
//             }
            steps {
                echo 'cron'
            }
        }
        stage("cCode") {
            when {
                expression { 
                    params.VERSION == 'cCode' 
                }
            }
            steps {
//                 script {
//                     gv.buildApp()
//                 }
                echo 'test'
            }
        }
        stage("pythonCode") {
            when {
                expression { 
                    params.VERSION == 'pythonCode' 
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
                    params.VERSION == 'bashCode' 
                }
            }
            steps {
//                 script {
//                     gv.buildApp()
//                 }
                echo 'test'
            }
        }
    }   
}
