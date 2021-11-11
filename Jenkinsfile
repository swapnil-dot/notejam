node{
    stage("Git cloning from BitBucket"){
        git 'https://swapnil9825@bitbucket.org/swapnil9825/notejam-mysql.git'
        
    }
    stage("SonarQube analysis"){
    environment {
        scannerHome = tool 'Sonar'
    }
        withSonarQubeEnv('Sonar'){
            sh '''/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/Sonar/bin/sonar-scanner \
            -D sonar.projectKey=nodejam \
            -D sonar.organization=swapnil9825 \
            -D sonar.host.url=https://sonarcloud.io \
            -D sonar.projectBaseDir=/var/lib/jenkins/workspace/pipeline \
            -D sonar.login=c2d27db4726ef31c9310b2fa5e98a4232e42abf9 \
            -D sonar.projectVersion=1.0 \
            -D sonar.sources=. \
            -D sonar.verbose=true'''
        }
    }
}




