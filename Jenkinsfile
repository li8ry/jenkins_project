VERSION = 'none'

pipeline {
    agent { node { label 'slave01' } }
    triggers {
        cron('* * * * *')
    }
    parameters {
        choice(name: 'VERSION', choices: ['Select from here', 'cCode', 'pythonCode', 'bashCode'], description: 'Chose code example to run')
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
                    params.VERSION == 'cCode' || params.VERSION == 'Select from here'
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
                    params.VERSION == 'pythonCode' || params.VERSION == 'Select from here'
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
                    params.VERSION == 'bashCode' || params.VERSION == 'Select from here'
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
