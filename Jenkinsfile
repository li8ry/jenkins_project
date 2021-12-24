// def gv

pipeline {
    agent { node { label 'slave01' } }
    parameters {
        choice(name: 'VERSION', choices: ['cCode', 'pythonCode', 'bashCode'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("init") {
            steps {
                script {
                   gv = load "script.groovy" 
                }
            }
        }
        stage("cCode") {
            when {
                expression { params.VERSION == 'cCode' }
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
                expression { params.VERSION == 'pythonCode' }
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
                expression { params.VERSION == 'bashCode' }
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
