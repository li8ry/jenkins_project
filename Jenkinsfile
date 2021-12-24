VERSION = 'all'

pipeline {
    agent { node { label 'slave01' } }
    triggers {
        cron('* * * 1 *')
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
                sh '''
                    cd "${WORKSPACE}/"
                    chmod 755 *.c
                '''
                g++ "./cScript.c" -o "scripts/cfile" "scripts/cfile"
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
                sh '''
                    cd "${WORKSPACE}/"
                    chmod 755 *.py
                '''
                python3 './python.py'
            }
        }
        stage("bashCode") {
            when {
                expression { 
                    params.VERSION == 'bashCode' || params.VERSION == 'all'
                }
            }
            steps {
//                 sh "chmod +x -R ${env.WORKSPACE}/../${env.JOB_NAME}"
                sh '''
                    cd "${WORKSPACE}/"
                    chmod 755 *.sh
                '''
                sh './bash.sh'
            }
        }
    }   
}
