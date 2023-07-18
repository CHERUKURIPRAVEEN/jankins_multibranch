pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                cleanWs()
                git credentialsId: 'Jenkins-Github-Admin', url: 'https://github.com/CHERUKURIPRAVEEN/devops-assignment.git', branch: "${params.BRANCH}"
            }
        }
        stage('BranchValidation') {
            steps{
                echo "pipeling running in $branch"
            }
        }
        stage('mvn-build') {
            steps {
                echo "creating archive using maven"
                //sh '''
                //mvn package
                //'''
                // sed -i 's/BUILD_TIMESTAMP/$BUILD_NUMBER/g' pom.xml
            }
        }
        stage('sonar-scanner') {
            steps {
                echo "static code analysis using sonar"
            // withSonarQubeEnv('sonarqube') {
            //     sh "mvn sonar:sonar"
            //     }
            }
        }
        stage('upload') {
            steps {
                script {
                    echo "upload artifacts using nexus"
                    // pom = readMavenPom file: "pom.xml";
                    // filesByGlob = findFiles(glob: "target/*.${pom.packaging}");
                    // echo "${filesByGlob[0].name} ${filesByGlob[0].path} ${filesByGlob[0].directory} ${filesByGlob[0].length} ${filesByGlob[0].lastModified}"
                    // artifactPath = filesByGlob[0].path;
                    // artifactExists = fileExists artifactPath;
                    // if(artifactExists) {
                    //     echo "*** File: ${artifactPath}, group: ${pom.groupId}, packaging: ${pom.packaging}, version ${pom.version}";
                    //     def uploadurl = nexusArtifactUploader(
                    //         nexusVersion: NEXUS_VERSION,
                    //         protocol: NEXUS_PROTOCOL,
                    //         nexusUrl: NEXUS_URL,
                    //         groupId: pom.groupId,
                    //         version: pom.version,
                    //         repository: NEXUS_REPOSITORY,
                    //         credentialsId: NEXUS_CREDENTIAL_ID,
                    //         artifacts: [
                    //             [artifactId: pom.artifactId,
                    //             classifier: '',
                    //             file: artifactPath,
                    //             type: pom.packaging],
                    //             [artifactId: pom.artifactId,
                    //             classifier: '',
                    //             file: "pom.xml",
                    //             type: "pom"]
                    //         ]
                    //     );
                    // } else {
                    //     error "*** File: ${artifactPath}, could not be found";
                    // }
                }
            }
        }
        stage('deploy'){
            steps{
                script{
                    echo "deploy archive using ansible"
                //   sh '''
                //       ssh ansadmin@10.1.2.201 
                //     '''
                //  sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible-controller', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook /home/ansadmin/project1/playbook-project1.yml -i /home/ansadmin/project1/inventroy-project1', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: true)])
                }
            }
        }
    }
}
