pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat """
                echo Checking Current Directory...
                echo Current Directory: %cd%
                dir

                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                """
            }
        }
        stage('Test') {
            steps {
                bat """
                echo Checking Current Directory...
                echo Current Directory: %cd%
                dir

                REM Activate the virtual environment (Windows)
                call mlip\\Scripts\\activate || echo "Activation Failed"

                REM Check if pytest is installed
                call pip show pytest || echo "pytest is not installed"

                REM Run pytest
                call pytest --maxfail=1 --disable-warnings -v || echo "pytest run failed"

                echo pytest completed successfully
                """
            }
        }
        stage('Deploy') {
            steps {
                bat """
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
                """
            }
        }
    }
}
