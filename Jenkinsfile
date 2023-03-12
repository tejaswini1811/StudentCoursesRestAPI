pipeline{
    agent{label 'workshop'}
    triggers{
        pollSCM( ' * * * * * ' )
    }
    stages{
        stage('vcs'){
            steps{
              git url: 'https://github.com/tejaswini1811/StudentCoursesRestAPI.git',
                branch: 'develop'
            }
        }
        stage('docker image build'){
            steps{
                sh 'docker image build -t teju1811/studentcourses:1.1 .'
            }
        }
        stage('scan and push'){
            steps{ 
                sh 'echo docker scan teju1811/studentcourses:1.1'
                sh 'docker image push teju1811/studentcourses:1.1'
            }
        }
        
    }
}
