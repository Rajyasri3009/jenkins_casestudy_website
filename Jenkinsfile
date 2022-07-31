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
            steps{
               echo 'For develop branch no publishing'
            }
        }
    }
}
