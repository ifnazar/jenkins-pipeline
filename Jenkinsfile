def clusters = ["clusterA", "clusterB", "clusterC"]
def jobs     = [:]


for (int i = 0; i < clusters.size(); i++) {
    def cluster = clusters[i]
    jobs["jobs-${cluster}"] = {
        node {
            stage("Build ${cluster}") {
			echo '${cluster} Testing..'
			sleep 60
			echo '${cluster} Testing..'
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
	 stage('XXXXXXXXXXX') {
            steps {
                script {
                    parallel jobs
                }
            }
        }        
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
