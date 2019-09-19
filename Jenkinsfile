pipeline{
agent any
stages{
stage('Builing the war file'){
steps {
sh 'mvn clean package'
}
post{
success{
echo "Builing archieve"
archiveArtifacts artifacts : "**/*.war"
}
}
}
stage('Deploy artifact to stage'){
    steps{
    build job : 'Deploy_Tomcat_Maven_Example_using_PipelineAsCode_Stage'
}
}
stage('Deploy changes to production'){
    steps{
    timeout(time: 5,unit:'DAYS'){
        input message: 'Approve Changes to Production?'
    }
    build job : 'Deploy_Tomcat_Maven_Example_using_PipelineAsCode_Production'
    }
    post{
        success{
            echo 'The build is successfully deployed to production'
        }
        failure{
            echo 'Deployment failure in PRODUCTION'
        }
    }
}
}
}
