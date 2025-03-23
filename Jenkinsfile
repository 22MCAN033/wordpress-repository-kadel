pipeline {
    agent any

    stages {
        stage('Clone WordPress Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/22MCAN033/wordpress-repository-kadel.git'
            }
        }

        stage('Deploy WordPress') {
            steps {
                sh """
                sudo cp -R * /var/www/html/
                sudo chown -R www-data:www-data /var/www/html
                sudo chmod -R 755 /var/www/html
                sudo systemctl restart apache2
                """
            }
        }
    }
}
