pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git, explicitly specifying the branch (main)
                git url: 'https://github.com/Harshini-programmer-2006/Features-data-set.git', branch: 'main'
            }
        }
        stage('Test Python') {
    steps {
        echo "Testing Python installation..."
        bat 'python --version'
    }
}

        stage('Setup Environment') {
            steps {
                echo "Creating virtual environment..."
                // Create Python virtual environment on Windows
                bat '"C:\\Program Files\\Python312\\python.exe" -m venv venv'
                
                echo "Activating virtual environment..."
                // Activate the virtual environment
                bat 'call venv\\Scripts\\activate.bat'
                
                echo "Installing dependencies..."
                // Install dependencies from requirements.txt
                bat 'venv\\Scripts\\pip.exe install -r requirements.txt'
            }
        }
    stage('Check Current Directory') {
            steps {
                echo "Current Directory:"
                bat 'cd'
            }
        }
        stage('Run Tests') {
            steps {
                echo "Running tests..."
                bat 'venv\\Scripts\\python.exe -m unittest discover -s tests -p "test*.py"'
            }
        }
        }
        stage('Deploy') {
            steps {
                echo "Deploying application..."
                // Add deployment steps here. For example, uploading processed data or results.
            }
        }
    }
    post {
        always {
            echo "Cleaning up workspace..."
            cleanWs() // Clean up the workspace after the pipeline is done
        }
    }
}


