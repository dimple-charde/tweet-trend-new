pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    stages {
        stage("Clone-code-dc"){
            steps {
                 git branch : 'main' , url: 'https://github.com/dimple-charde/tweet-trend-new.git'
           		 }
        	}
        
	}
}
