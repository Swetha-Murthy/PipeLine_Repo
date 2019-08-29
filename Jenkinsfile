<<<<<<< HEAD
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
=======
pipeline {
    agent any

    stages {

        stage('SCM Checkout') {
            steps {
                git credentialsId: '8e237d54-cc07-4aad-a3fe-51855a4d84c1', url: 'https://github.com/pramodk05/java_maven_jenkins.git'
            }
        }

        stage('Compile Stage') {
            steps {
                withMaven(maven : 'maven_3.6') {
                    sh 'mvn clean compile'
                }
            }
        }

        
        stage('Test Stage') {
            steps {
                withMaven(maven : 'maven_3.6') {
                    sh 'mvn test'
                }
            }
        }

        
        stage('Create the Build artifacts Stage (Package)') {
            steps {
                withMaven(maven : 'maven_3.6') {
                    sh 'mvn package'
                }
            }
        }

        stage('Deployment Stage - Tomcat Container') {
            steps {
                deploy adapters: [tomcat8(credentialsId: 'f5c26087-bdee-4306-967a-6ae8eeec19d0', path: '', url: 'http://3.83.255.30:8080')], contextPath: 'mvn-hello-world', war: 'target/*.war'
            }
        }
        
    }
>>>>>>> f7aefdeca7507ff6d46ebe3e0871639d2ba323c2
}
