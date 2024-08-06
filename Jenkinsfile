node {
    try {
        stage('Checkout') {
            checkout scm
        }
        
        stage('Build') {
            sh 'mvn clean install'
        }
        
        stage('Test') {
            sh 'mvn test'
        }
        
        stage('Deploy') {
            sh 'mvn deploy'
        }
    } catch (Exception e) {
        currentBuild.result = 'FAILURE'
        throw e
    } finally {
        echo 'This will always run'
    }
    
    if (currentBuild.result == 'SUCCESS') {
        echo 'This will run only if successful'
    } else {
        echo 'This will run only if failed'
    }
}
