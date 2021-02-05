node('security-scanner') {
    stage('Pre-flight security scan') {
        checkout scm
        sh '/usr/local/bin/security-scan.sh'
    }
}
try {
    node {
        stage('Prepare Jenkinsfile environment') {
            checkout scm
        }
        // now that SCM is checked out we can load and execute the repository
        // Jenksinfile
        load 'Jenkinsfile'
    }
} catch(Exception e) {
    throw e
} finally {
    stage('Post-run auditing') {
        // do some audit stuff here
    }
}
