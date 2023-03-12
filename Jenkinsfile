pipeline {
    agent { label 'node1' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/Mypracticeclassoct-dec/StudentCoursesRestAPI-devopsmarch11.git',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t vamsibakka/spc1:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh ' docker scan vamsibakka/spc1:latest'
                sh 'docker image push vamsibakka/spc1:latest'
            }
        }
    }

}