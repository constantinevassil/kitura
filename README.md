# Kitura - deployment on Google Cloud Run


Creating a Kitura project with the macOS App
1) Visit
https://www.kitura.io/app.html

Download and install Kitura - macOS App

2) Run Kitura - macOS App.
Select the Starter template and click on Create.
Use name hellokituragcr (small caps)

Starter: This builds on top of Skeleton and provides a full-fledged server framework that includes logging, monitoring and health checks. It also provides configuration files for Docker, Kubernetes and more.


3) Open the terminal and perform the command:
cd hellokituragcr

4) Install Kitura CLI
brew tap ibm-swift/kitura
brew install kitura

This will initialize your CLI environment:
kitura idt

This will take a few moments to build a Docker image
kitura build

Now run kitura run. This builds then runs a hellokituragcr-swift-run image optimized for production usage.
kitura run

Your Kitura app is up and running as a Docker image. Open your browser to http://localhost:8080/ to see it running

Deploy to Google Cloud Run

1) Upload to Container Registry

gcloud builds submit --tag gcr.io/<my project ID>/hellokituragcr

gcloud container images list

2) Deploy Container to Google Cloud Run  

gcloud beta run deploy --image gcr.io/<my project ID>/hellokituragcr --memory 512M --platform managed --allow-unauthenticated


The deployment is not working. We are in process of figuring out why.

Deployment failed                                                                                                                 
ERROR: (gcloud.beta.run.deploy) Cloud Run error: Container failed to start. Failed to start and then listen on the port defined by the PORT environment variable. Logs for this revision might contain more information.
