def GIT_URL="https://github.com/wipas-p/CoreTest.git"

pipeline {
    agent any
    
    stages {
    stage ('GET-Source Code') {
      steps {
        script {
          echo "Checkout SCM"
          git branch: 'master', url: 'https://github.com/wipas-p/CoreTest.git'
          // withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: "${GIT_CRED_ID}", usernameVariable: 'GITLAB_User', passwordVariable: 'GITLAB_Password']]) {
          //   sh "git clone https://${GITLAB_User}:${GITLAB_Password}@${GIT_URL}"
        }
      }
    }

    // stage ('Compile Code') {
    //   steps {
    //     echo "Compile"
    //     sh 'cd DemoSpringBoot && mvn clean install -DskipTests=true'
    //   }
    // }
    
    stage ('Build Image') {
      steps {
        echo "Build Image"
        echo "Now Perform Build Docker Image Steps"
        // sh "sudo docker login ${dockerLogin}"
        // sh "sudo docker build -t ${dockerRepoURL}/${dockerRepo}/demoapp:devlatest ."
        sh "sudo docker build -t kong/coretest ."
        // sh "sudo docker push ${dockerRepoURL}/${dockerRepo}/demoapp:devlatest"
      }
    }

    stage ('Deploy DEV') {
      steps {
          echo "Deploy DEV"
          }
    }
    
    stage ('Test') {
      steps {
          echo "Testing"
          }
    }    
    
    }
    
}
