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
}
}

