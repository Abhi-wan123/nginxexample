pipeline {
   agent { label 'nginx' }
   triggers {
       pollSCM '* * * * *'
   }
    stages {
        stage('scm') {
            steps {
                sh 'git clone https://github.com/abhijeetwankhade3108/apache-example.git'
                echo env.BRANCH_NAME
                echo env.BUILD_NUMBER
                echo env.BUILD_ID
            }
        }
        stage('remove file forcefully') {
            steps {
                sh "sudo rm -rf /var/www/html/*"
            }
        }
        stage('copy files recursively') {
            steps {
                sh "sudo cp -R apache-example/www/index.html /var/www/html/"
            } 
        } 
    }
}