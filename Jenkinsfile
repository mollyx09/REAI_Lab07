pipeline {
    agent any

    stages {
        stage('Build') {
            steps {                
                echo 'Start Build'
            }
        }
        stage('Test') {
            steps {
                bat '''
                echo Test Step: Running pytest in virtual environment 'mlip'
                
                call mlip\\Scripts\\activate

                pip show pytest

                python -m pytest

                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
