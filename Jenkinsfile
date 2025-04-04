pipeline {
    agent any

    stages {
        stage('Build') {
            steps {                
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
            }
        }
        stage('Test') {
            steps {
                bat '''
                echo Test Step: Running pytest in virtual environment 'mlip'
                
                call .venv\\mlip\\Scripts\\activate

                pip show pytest

                python -m pytest


                echo pytest completed successfully
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
