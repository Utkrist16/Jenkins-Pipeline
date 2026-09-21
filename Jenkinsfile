pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')   // checks GitHub for new commits every 5 minutes
    }

    stages {

        stage('1. Build') { // testing auto trigger
            steps {
                echo "Task: Compile and package the application code."
                echo "Tool: Maven"
            }
        }

        stage('2. Unit and Integration Tests') {
            steps {
                echo "Task: Run unit tests to check individual functions, and integration tests to check components work together."
                echo "Tool: JUnit (unit tests) and Postman/Newman (integration tests)"
            }
        }

        stage('3. Code Analysis') {
            steps {
                echo "Task: Analyse code quality against industry standards."
                echo "Tool: SonarQube"
            }
        }

        stage('4. Security Scan') {
            steps {
                echo "Task: Scan code and dependencies for known vulnerabilities."
                echo "Tool: OWASP Dependency-Check"
            }
        }

        stage('5. Deploy to Staging') {
            steps {
                echo "Task: Deploy the built application to a staging server for pre-production testing."
                echo "Tool: AWS EC2 (via AWS CLI / Ansible)"
            }
        }

        stage('6. Integration Tests on Staging') {
            steps {
                echo "Task: Run integration tests against the staging environment to confirm production-like behaviour."
                echo "Tool: Selenium"
            }
        }

        stage('7. Deploy to Production') {
            steps {
                echo "Task: Deploy the verified application to the live production server."
                echo "Tool: AWS EC2 (via AWS CLI / Ansible)"
            }
        }
    }
}
