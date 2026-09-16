pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/yashtibarri5-bot/jenkins.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    sudo rm -rf /var/www/html/*
                    sudo cp -r ./* /var/www/html/
                    sudo chown -R www-data:www-data /var/www/html
                    sudo chmod -R 755 /var/www/html
                    sudo systemctl restart apache2
                '''
            }
        }
    }
}
