pipeline {
    agent any

    environment {
    
        global_name = 'Prasanta'
    }
    
    parameters {
        
        string(name: "Enter_your_name", description: "Please try to enter your name")
        booleanParam(name: "isMale")
        choice(name: "City", choices: [ 'BBSR','CTC','KPARA' ])
    }

    stages {
        
        
        stage('In-build variable') {
            steps {
                
                echo "$BUILD_ID"
            }
        }
        stage('Global variable') {
            steps {
                
                echo "$global_name"
            }
        }
        stage('Local variable') {
            
            environment {
                local_name = "Akash"
            }
            
            steps {
                
                echo "$local_name"
            }
        }
        
        stage('User inputs') {
            
           steps {
                
                sh '''
                echo "Yor name is : $Enter_your_name"
                echo "Are you a male : $isMale"
                echo "You are from : $City"
                '''
            }
        }
        
        stage('Are you sure ?') {
            
            input {
                message "Do you want to continue ?"
                ok "Go......."
            }
            
            steps {
                
                echo "Prod deployment done"
            }
        }
        
    }
    
    post {
        
        always {
            
            echo "Always Hi..........."
        }
        
        failure {
            
            echo "I am failed....."
        }
        
        success {
            
            echo "I am success....."
        }
    }
    
    
}
