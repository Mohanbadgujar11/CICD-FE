pipeline{

    agent any

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
                sudo cp -r dist/* /var/www/html/
                sudo systemctl restart nginx
                '''
            
            }
        }
    }

}