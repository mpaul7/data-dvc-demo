# Data DVC Demo
Data version control using DVC
 
 ## How to install gsutil
 Ref: https://cloud.google.com/storage/docs/gsutil_install#deb
 ```sh
 $ sudo apt-get update
 $ sudo apt-get install apt-transport-https ca-certificates gnupg curl
 $ curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg
 $ curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
 $ echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
 $ sudo apt-get update && sudo apt-get install google-cloud-cli
$ gloucd init
$ gcloud projects create dvc-demo
# Enable billing for your project in Google Cloud Console
# https://console.cloud.google.com/billing
$ gcloud auth application-default set-quota-project mai-dvc-demo
$ gsutil ls gs://mai-dvc-demo
$ gcloud config set project <PROJECT_ID>
 ```
## How to setup DVC project

```sh
$ git clone <repo-url>
$ cd <repo-name>
$ dvc init
$ pip install dvc-gs
$ git status
$ git add .
$ git commit -m "Initial commit"
$ git branch -M main
$ git remote add origin <repo-url>
$ git remote -v
$ git push -u origin main
```
### Add git repository to DVC
```sh
$ dvc remote add <remote-name> <remote-url>
$ dvc remote add <remote-name> <remote-url>
```

### Push data to DVC
```sh
$ dvc add <file-name>
$ dvc push
```s
