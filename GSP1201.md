# Build a Chat Application using the PaLM 2 API on Cloud Run || GSP1201

## Solution [here](https://youtu.be/gnRrAbUzMdc)

### Run the following Commands in the Cloud shell


```
export REGION=
```

```
gsutil cp -R gs://spls/gsp1201/chat-flask-cloudrun .

cd chat-flask-cloudrun

export PROJECT_ID=$DEVSHELL_PROJECT_ID


export AR_REPO='chat-app-repo'
export SERVICE_NAME='chat-flask-app'

gcloud artifacts repositories create "$AR_REPO" --location="$REGION" --repository-format=Docker

gcloud builds submit --tag "$REGION-docker.pkg.dev/$PROJECT_ID/$AR_REPO/$SERVICE_NAME"

gcloud run deploy "$SERVICE_NAME" --port=8080 --image="$REGION-docker.pkg.dev/$PROJECT_ID/$AR_REPO/$SERVICE_NAME:latest" --allow-unauthenticated --region=$REGION --platform=managed --project=$PROJECT_ID --set-env-vars=GCP_PROJECT=$PROJECT_ID,GCP_REGION=$REGION
```



### Congratulations 🎉 for completing the Lab !

##### You Have Successfully Demonstrated Your Skills And Determination.

#### *Well done!*

#### Don't Forget to Join the [Telegram Channel](https://t.me/cloudstars24)

### Subscribe to our YouTube Channel [CLOUD STARS](https://www.youtube.com/@cloud-stars)
