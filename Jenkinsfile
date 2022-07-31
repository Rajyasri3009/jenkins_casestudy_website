pipeline{
    agent any
    stages{
        stage('gitcheckout'){
            steps{
                echo 'checkout git repo'
                checkout([$class: 'GitSCM', branches: [[name: '*/develop']], extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'mygitbackup']], userRemoteConfigs: [[ url: 'https://github.com/Rajyasri3009/jenkins_casestudy_website.git']]])
            }
        }
        stage('build'){
            steps{
                echo 'build process complete '+BRANCH_NAME
            }
        }
        stage('publish'){
            when{
                expression{
                    BRANCH_NAME=='master'
                }
            }
            steps{
               echo 'Copy files to html folder'
                sh 'cp -r /var/lib/jenkins/workspace/dev-cms/mygitbackup/* /var/www/html'
            }
        }
    }
}
