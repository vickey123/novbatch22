pipeline {
    agent any
    stages{
      stage('Checkout external proj') {
        steps {
            git branch: 'main',
                credentialsId: '9a3c51bc-3642-4ef6-bbdb-160d1099ac89',
                url: 'https://github.com/vickey123/novbatch22.git'

            sh "ls -lat"
        }
    }
    } 
      stage("Run cloudformaiton stack") {
        steps{  
           withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: '	awscredentials', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY']]) {
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml
             '''
    }
  }
}
}
        
    

