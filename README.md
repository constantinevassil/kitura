# kitura

gcloud builds submit --tag gcr.io/<My projectID>/hellokituragcr
gcloud beta run deploy --image gcr.io/<My projectID/hellokituragcr --platform managed

Deployment failed                                                                                                                 
ERROR: (gcloud.beta.run.deploy) Cloud Run error: Container failed to start. Failed to start and then listen on the port defined by the PORT environment variable. Logs for this revision might contain more information.
