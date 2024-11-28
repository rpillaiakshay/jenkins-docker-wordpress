pipeline {
    agent any
    stages {
        stage('Get the GitHub Url') {
            steps {
                git url: 'https://github.com/rpillaiakshay/jenkins-docker-wordpress.git', branch: "master"
            }
        }
        stage('Run the docker compose') {
            steps {
                sh 'echo "asd123." | sudo -S docker compose -f sql-wordpress.yaml up -d'
            }
        }
    }
}
