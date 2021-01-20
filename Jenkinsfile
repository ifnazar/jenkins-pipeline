def clusters = ["clusterA", "clusterB", "clusterC", "clusterD", "clusterE", "clusterF", "clusterG", "clusterH", "clusterI", "clusterJ", "clusterL", "clusterM", "clusterN", "clusterO", "clusterP", "clusterQ", "clusterR", "clusterS", "clusterT"]
def jobsA     = [:]
def jobsB     = [:]



for (int i = 0; i < clusters.size(); i++) {
    def cluster = clusters[i]
    jobsA["jobs-${cluster}"] = {
        node {
            stage("init ${cluster}") {
			echo '${cluster} Testing..'
			sleep 10
			echo '${cluster} Testing..'
            }
        }
    }
}

for (int i = 0; i < clusters.size(); i++) {
    def cluster = clusters[i]
    jobsB["jobs-${cluster}"] = {
        node {
            stage("plan ${cluster}") {
			echo '${cluster} Testing..'
			sleep 20
			echo '${cluster} Testing..'
            }
        }
    }
}



pipeline {
    agent any

    stages {
        stage('Build/Test Manager') {
            steps {
                echo 'Building..'
            }
        }
	 stage('INIT') {
            steps {
                script {
                    parallel jobsA
                }
            }
        }
	 stage('PLAN') {
            steps {
                script {
                    parallel jobsA
                }
            }
        }        
    }
}
