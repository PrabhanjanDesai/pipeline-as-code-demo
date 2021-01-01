
pipeline {
    
    agent {
        node {
            label 'master'
        }
    }

    tools { 
        maven 'M2_HOME' 
    }

    options {
        buildDiscarder logRotator( 
                    daysToKeepStr: '15', 
                    numToKeepStr: '10'
            )
    }

    
    stages {
        
        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/master']], 
                    userRemoteConfigs: [[url: 'https://github.com/spring-projects/spring-petclinic.git']]
                ])
            }
        }

        
       stage('Priting All Global Variables') {
            steps {
                sh """
                env
                """
            }
        }
        
        stage('Printing Test') {
            steps {
                echo 'Testing this message through pipeline'
            }
        }
        
        
    }   
}
