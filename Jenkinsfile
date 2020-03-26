pipeline {
	agent any
	stages {
		stage('Upload to AWS') {
			steps {
				withAWS(credentials: 'aws-static', region: 'us-east-1') {
					echo "Hello AWS"
					s3Upload(file: 'index.html', bucket: 'hchen1991-jenkins', path: '.')
				}

				sh 'echo "Hello World"'
				sh '''
					echo "Multiline shell steps works too"
					ls -lah
				'''
			}
		}
	}
}
