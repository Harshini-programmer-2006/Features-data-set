pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub
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
                bat 'venv\\Scripts\\pip.exe install -r requirements.txt' // Install Python dependencies
            }
        }
        stage('Process Dataset') {
            steps {
                echo "Processing the dataset..."
                // Assuming you have a Python script that processes the dataset (e.g., process_data.py)
                bat 'venv\\Scripts\\python.exe process_data.py /mnt/data/Features\\ data\\ set.csv'
            }
        }
        stage('Run Tests') {
            steps {
                echo "Running tests..."
                // Example: running tests on the processed data
                // You can replace this with pytest or any testing framework of your choice
                bat 'venv\\Scripts\\python.exe -m unittest discover'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the processed data or application..."
                // Add your deployment commands here
                // For example, uploading results or processed data to a server
            }
        }
    }
    post {
        always {
            echo "Cleaning up workspace..."
            cleanWs() // Clean up the workspace after the pipeline
        }
    }
}
