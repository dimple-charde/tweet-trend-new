pipeline {
    agent {
        node {
            label 'maven'
        }
    }
<<<<<<< HEAD
environment {
    PATH ="/opt/apache-maven-3.9.6/bin:$PATH"
=======

    stages {
        stage("Clone-code-dc"){
            steps {
                 git branch : 'main' , url: 'https://github.com/dimple-charde/tweet-trend-new.git'
           		 }
        	}
        
	}
>>>>>>> b55a3390a3258b0cf68ce3d70425d428e246926f
}
    stages {
        stage("build"){
            steps {
                echo "----------- build started ----------"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                 echo "----------- build complted ----------"

            }
        }
        stage("test") {
            steps {
                echo "----------- unit test started ----------"
                sh 'mvn surefire-report:report'
                 echo "----------- unit test Complted ----------"

            }
        }
        stage('SonaQube Analysis'){
            environment {
                scannerHome = tool 'sonar-scanner'
            }
            steps {
                withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
                    sh "${scannerHome}/bin/sonar-scanner"

            }
        }
    }
}
}