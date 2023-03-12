pipeline {
    agent { label 'docker' }
    triggers { 
        pollSCM('* 23 * * 1-5')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/Mypracticeclassoct-dec/StudentCoursesRestAPI-devopsmarch11.git',
                    branch: 'sprint_1_release'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t vamsibakka/spc2:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'docker scan vamsibakka/spc2:latest'
                sh 'docker image push vamsibakka/spc2:latest'
            }
        }
    }

}