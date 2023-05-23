pipeline {
    agent any
    parameters{
        string (name:'VERSION', defaultValue: '' ,description:'專案版本')
        choice (name:'APP_PLATFORM', choices: ['android','ios'], description:'app開發平台')
        booleanParam (name:'EXECUTE_TASK' , defaultValue: true , description:'是否執行任務x')
    }
    stages {
        stage('Build') {
            steps {
                // 在這裡定義你的建置步驟
                sh 'echo "Building..."'
            }
        }
        
        stage('Test') {
            steps {
                // 在這裡定義你的測試步驟
                sh 'echo "Testing..."'
            }
        }
        
        stage('Deploy') {
            steps {
                // 在這裡定義你的部署步驟
                sh 'echo "Deploying..."'
            }
        }
    }
}