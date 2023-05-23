String workspace = "/var/lib/jenkins/workspace/my-multi-pipline_main"
pipeline {
    agent any
    parameters{
        string (name:'VERSION', defaultValue: '' ,description:'專案版本')
        choice (name:'APP_PLATFORM', choices: ['android','ios'], description:'app開發平台')
        choice (name:'BRANCH', choices: ['main','new_feature'], description:'要clone下來的branch')
        booleanParam (name:'EXECUTE_TASK' , defaultValue: true , description:'是否執行任務x')
    }
    
    stages {
        stage("Print") {
            steps {
                echo "VERSION: ${params.VERSION}"
                echo "APP_PLATFORM: ${params.APP_PLATFORM}"
                echo "EXECUTE_TASK: ${params.EXECUTE_TASK}"
            }
        }
        stage('Build') {
            steps {
                script {
                    sh "echo ${workspace}"
                    sh "rm -R -f ${workspace}/svn_source_*"
                    if (params.APP_PLATFORM == "android") {
                        dir('svn_source_' + params.APP_PLATFORM) {
                            sh "git clone -b ${params.BRANCH} https://github.com/10556053/jenkins-practice.git"
                        }
                    } else if (params.APP_PLATFORM == "ios" ) {
                        dir('svn_source_' + params.APP_PLATFORM) {
                            sh "git clone -b ${params.BRANCH} https://github.com/10556053/jenkins-practice.git"
                        }
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script{
                    // 在這裡定義你的測試步驟
                    sh 'echo "Testing..."'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script{
                    // 在這裡定義你的部署步驟
                    sh 'echo "Deploying..."'
                }
            }
        }
    }
}
