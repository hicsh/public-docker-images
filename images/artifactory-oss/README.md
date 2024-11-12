```
helm repo add artifactory-oss https://charts.jfrog.io 
helm repo update artifactory-oss
helm template artifactory-oss/artifactory-oss --version 107.29.7 \
    | yq '..|.image? | select(.)' \
    | sort -u

helm template artifactory-oss/artifactory-oss --version 107.29.7 | grep 'image: ' | grep artifactory-oss | sort -u

```