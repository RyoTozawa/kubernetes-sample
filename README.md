# kubernetes-sample
## Purpose
Try to deploy web service on HTTPS
## Environment
- GCP
    - Cloud Build
    - Cloud SQL
    - Cloud Registry
    - Google Kubenetes Engine
    - Google Compute Engine
## Deploy Step
### 1. Issue credential file to GKE cluster 
[Please Read Official Page](https://cloud.google.com/sql/docs/container-engine-connect?hl=ja)
### 2. Get static global ip from GCE
You can get static GIP by using kubernetes-ingress from key  
{RUN THIS COMMAND}  
`gcloud compute addresses create kubernetes-ingress --global`
### 3. Make Domain
1. Set static GIP on A Record of Google Cloud DNS
2. Set Domain & Tell Google Cloud DNS Four Name Servers
### 4. Set `/` path on your api server for Healthcheck
add Routhing `/` path which return status 200
> Ingree check server's status to ping `/` path everytime.  

EOF
## Reference
- [GKE でサービスを HTTPS と HTTP/2 に対応する(kube-lego 編)](https://qiita.com/apstndb/items/2fef0a80d4510516cb1f)