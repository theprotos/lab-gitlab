# Gitlab

## DinD for kubernetes runner

1. Clone this repo to Gitlab.com project
2. Create <token> in Gitlab UI [USER] > [REPO] > [CI/CD Settings] > [New runner]
3. Deploy runner to k8s
    ```bash
    kubectl create ns gitlab
    helm repo add gitlab https://charts.gitlab.io/
    helm repo update
    
    helm upgrade -i gitlab-runner \
        --set gitlabUrl=https://gitlab.com,runnerRegistrationToken=<token> \
        gitlab/gitlab-runner \
        -n gitlab \
        -f values.yaml
    ```
4. CI/CI pipeline should start automatically.
