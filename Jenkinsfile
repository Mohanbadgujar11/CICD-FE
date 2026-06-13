pipeline{

    agent any

    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh ''' 
                cp -r dist/* /var/www/html/
                sudo systemctl restart nginx
                '''
            
            }
        }
    }

}