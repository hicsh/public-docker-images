```
helm repo add artifactory-jcr https://charts.jfrog.io 
helm repo update artifactory-jcr
helm template artifactory-jcr/artifactory-jcr --version 107.29.7 \
    | yq '..|.image? | select(.)' \
    | sort -u

helm template artifactory-jcr/artifactory-jcr --version 107.29.7 | grep 'image: ' | grep artifactory-jcr | sort -u

```