pipeline{
agent any
stages{
stage('Builing the war file'){
steps {
mvn clean package
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

