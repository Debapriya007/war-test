node('slave'){
    
    stage( 'code checkout'){
        echo 'checking the code from git repo'
        git 'https://github.com/shubhamkushwah123/war-test.git'
    }
    stage( 'code build'){
        echo 'code building process'
        sh 'mvn clean package'
        
    }
    stage( 'code deploy'){
        echo 'code deployed'
        deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://172.31.83.236:8081/')], contextPath: 'war-test', war: '**/*.war'
    }
    
}
