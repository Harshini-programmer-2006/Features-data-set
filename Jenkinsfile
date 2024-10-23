pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git
                git url: 'https://github.com/Harshini-programmer-2006/Features-data-set.git'
            }
        }
        stage('Setup Environment') {
            steps {
                echo "Creating virtual environment..."
                bat 'C:\\Users\\Windows\\AppData\\Local\\Programs\\Python\\Python312\\python.exe -m venv venv' // Create virtual environment
                echo "Activating virtual environment..."
                bat 'call venv\\Scripts\\activate.bat' // Activate virtual environment
                echo "Installing dependencies..."
                bat 'C:\\Users\\Windows\\AppData\\Local\\Programs\\Python\\Python312\\Scripts\\pip.exe install -r requirements.txt' // Install dependencies
            }
        }
        stage('Process Dataset') {
            steps {
                echo "Processing dataset..."
                // Add your dataset processing script here
                bat 'python process_dataset.py /mnt/data/Features\\ data\\ set.csv' // Run a script to process the dataset
            }
        }
        stage('Run Tests') {
            steps {
                echo "Running tests..."
                // Add your testing commands here
                bat 'pytest' // Example: Run tests
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying application..."
                // Add your deployment commands here
            }
        }
    }
    post {
        always {
            echo "Cleaning up workspace..."
            cleanWs() // Clean up workspace
        }
    }
}
