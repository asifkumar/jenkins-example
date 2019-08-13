pipeline {
    agent any

    try {
		stages {
			stage ('Compile Stage') {

				steps {                
					    sh 'mvn clean compile'
                				}
			}
			stage ('Testing Stage') {

				steps { 
					    sh 'mvn test'
                }
			}
			stage ('Deployment Stage') {
				steps {  
					    sh 'mvn deploy'
                }
			}
		}
    } catch (err) {
		emailtext body: "$(err)", subject : 'failure', to: 'asifdevops@gmail.com'
		
	}
		
}
