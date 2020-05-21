pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
	  stage('Docker Build') {
         steps {
            pwsh(script: 'docker images -a')
			pwsh(script: """
				cd docker/
				docker build -t jenkins-pipeline .
				docker images -a
				cd ..
			""")
         }
      }
   }
}
