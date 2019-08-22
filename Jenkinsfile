pipeline{
    agent any
    stages {
        stage('SCM checkout') {
            steps {
            echo "Checking out from the Source Repository"
            git url: 'https://github.com/pramodk05/java_maven_jenkins'
            }
        }
    
    stage('compile stage') {
            steps {
            echo "compiling the code"
            withMaven(maven: 'Maven_3.6') {
            sh 'mvn compile'    
            }
            
        }

    }

stage('Test Stage') {
            steps {
            echo "Testing the source"
            withMaven(maven: 'Maven_3.6') {
            sh 'mvn test'
            }
    }
}


stage('package stage') {
            steps {
            echo "packaging the source"
            withMaven(maven: 'Maven_3.6') {
            sh 'mvn package'
            }
            }
}
stage('deploy stage') {
            steps {
            echo "deploying the source"
            deploy adapters: [tomcat8(credentialsId: '1054e14a-ab14-494b-ba12-744ff9a3b02b', path: '', url: 'http://54.234.255.6:9090')], contextPath: 'maven-hello-world', war: 'target/*.war'
            
            }
            }

}
}
