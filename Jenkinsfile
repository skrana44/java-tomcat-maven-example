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
stage('Deploy artifact'){
    build job : 'Deploy_Tomcat_Maven_Example_using_PipelineAsCode_Stage'
}
}
}
