pipeline {
    agent {label 'jenkins-jenkins-slave '}
    triggers {
        cron('10 0 * * *')
    }
    stages {
        stage('Preparation') {
                    steps{
                        echo "1.Prepare Stage"
                        checkout scm
                        script {
                            git_tag = sh(returnStdout: true, script: 'git rev-parse --short HEAD').trim()
                            build_tag = "${env.BRANCH_NAME}-${git_tag}"
                            loginName = "admin"
                            loginPassword = "Harbor12345"
                            echo "branch: ${env.BRANCH_NAME}"
                            echo "build tag: ${build_tag}"
                        }
                    }

        }
        stage('login oc & docker regristry') {
            steps{
                echo "2.login oc & docker regristry"
                
                sh "docker login -u '${loginName}' -p '${loginPassword}' http://10.7.12.250/harbor/projects"
            }

        }
        stage('Build') {
            steps{
                echo "3.Maven Build Stage"
                sh "mvn clean install -DskipTests"
                // sh "mvn clean build -DskipTests"
                sh "docker build -f src/docker/Dockerfile -t http://10.7.12.250/nana_test/test:latest ."
                // docker build -f src/docker/Dockerfile .
                sh "docker push docker push 10.7.12.250/nana_test/test:latest"
            }
        }

    }
}
