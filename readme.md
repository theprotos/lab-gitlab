# Gitlab

## DinD for kubernetes runner

Create <tocken> in Gitlab UI [USER] > [REPO] > [CI/CD Settings] > [New runner]


```
kubectl create ns gitlab
helm repo add gitlab https://charts.gitlab.io/
helm repo update

helm upgrade -i gitlab-runner \
    --set gitlabUrl=https://gitlab.com,runnerRegistrationToken=glrt-9MYXYksQB7MDTpU5xg_y \
    gitlab/gitlab-runner \
    -n gitlab \
    -f values.yaml
```   
