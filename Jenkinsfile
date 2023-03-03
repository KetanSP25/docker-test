pipeline{
	agent{ 
			label {
					label 'built-in'
					customWorkspace '/mnt/project'
				}
		}		
	stages{
		stage('getting file1'){
			steps{
				sh "rm -rf *"
				dir('/mnt/project/22Q1'){
					sh "git clone https://github.com/KetanSP25/docker-test.git -b 22Q1"
					sh "rm -rf /mnt/project/22Q1/docker-test/Jenkinsfile"
					sh "chmod -R 777 /mnt/project/22Q1/docker-test/index.html"
								 	}
				}
		}
		stage('deploying on container 1'){
			steps{
				sh "docker run -itdp 80:80 --name 22Q1 httpd"
				sh "docker cp /mnt/project/22Q1/docker-test/index.html 22Q1:/usr/local/apache2/htdocs/index.html"
			}
		}
		stage('getting file 2'){
			steps{
				sh "rm -rf *"
				dir('/mnt/project/22Q2'){
					sh "git clone https://github.com/KetanSP25/docker-test.git -b 22Q2"
					sh "rm -rf /mnt/project/22Q2/docker-test/Jenkinsfile"
					sh "chmod -R 777 /mnt/project/22Q2/docker-test/index.html"
								 	}
				}
		}
		stage('deploying on container2'){
			steps{
				sh "docker run -itdp 90:80 --name 22Q2 httpd"
				sh "docker cp /mnt/project/22Q2/docker-test/index.html 22Q2:/usr/local/apache2/htdocs/index.html"
			}
		}
		stage('getting file 3'){
			steps{
				sh "rm -rf *"
				dir('/mnt/project/22Q3'){
					sh "git clone https://github.com/KetanSP25/docker-test.git -b 22Q3"
					sh "rm -rf /mnt/project/22Q3/docker-test/Jenkinsfile"
					sh "chmod -R 777 /mnt/project/22Q3/docker-test/index.html"
								 	}
				}
		}
		stage('deploying on container 3'){
			steps{
				sh "docker run -itdp 81:80 --name 22Q3 httpd"
				sh "docker cp /mnt/project/22Q3/docker-test/index.html 22Q3:/usr/local/apache2/htdocs/index.html"
			}
		}
	
	}
}
