pipeline{
agent any
stages{
stage('Builing the war file'){
steps {
sh 'mvn clean package'
}
post{
success{
echo "Builing archice
archiveArtifact artifact : "**/*.war""
}
}
}
}
}

