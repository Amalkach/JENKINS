pipeline {
 agent any
 stages {
 stage("Build") {
 steps {
 echo "Gradle Buliding"
 }
 }
 stage("Unit and Integration Tests") { 
 steps {
 echo "Test Running"
 echo "Integration running"
 }
 post {
 success {
 emailext attachLog: true,
 subject: "Completed both the tests",
 body: "Completed both the tests",
 to: "amalkachappilly07@gmail.com"
 }
 failure {
 emailext attachLog: true,
 subject: "Fail both the tests",
 body: "Failed both the tests",
 to: "amalkachappilly07@gmail.com"
 }
 }
 }
 stage("Code Analysis") {
 steps {
 echo " Analyzing code quality using SonarQube"
 }
 }
 stage("Security Scan") {
 steps {
 echo "Performing security scan with OWASP ZAP"
 }
 post {
 success {
 emailext attachLog: true,
 subject: "Completed security scan",
 body: "Completed security scan",
 to: "amalkachappilly07@gmail.com"
 }
 failure {
 emailext attachLog: true,
 subject: "Failed security scan",
 body: "Failed security scan",
 to: "amalkachappilly07@gmail.com"
 }
 }
 }
 stage("Deploy to Staging") {
 steps {
 echo "Staging environment Deploying using Kubernetes"
 }
 }
 stage("Integration Tests on Staging") {
 steps {
 echo "integration tests Running on Staging environment"
 }
 }
 stage("Deploy to Production") {
 steps {
 echo "Deploying Production Deployment with Kubernetes"
 }
 }
 }
 post {
 success {
 emailext attachLog: true,
 subject: "Pipeline successdd",
 body: "Pipeline has been created successfully!",
 to: "amalkachappilly07@gmail.com"
 }
 failure {
 emailext attachLog: true,
 subject: "Pipeline failed",
 body: "The pipeline has failed. Please take necessary actions.",
 to: "amalkachappilly07@gmail.com"
 }
 }
}
