pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'default maven') {
                    sh 'mvn --settings settings.xml clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'default maven') {
                    sh 'mvn --settings settings.xml package'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'default maven') {
                    sh 'mvn --settings settings.xml deploy'
                }
            }
        }
    }
}
