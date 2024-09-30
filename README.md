

This repository contains the necessary configurations to deploy a node red with OIDC Support in your Kubernetes Cluster

## Installation

Follow these simple steps to get node-red running.

### Step 1: Fill in the Kubernetes Secrets

1. Open the `node-red-secret.yml` file located in this repository.
2. Replace the placeholder values with your values. Here's a snippet for reference:
echo -n 'YOUR_SECRET_VALUE' | base64
    ```yaml
    apiVersion: v1
    kind: Secret
    metadata:
      name: node-red-secret
    type: Opaque
    data:
      OAUTH_AUTH_URL: <BASE64_ENCODED>
      OAUTH_TOKEN_URL: <BASE64_ENCODED>
    ```


### Step 2: Deploy the Secret and the Kubernetes-Deployment

1. Once your `secrets.yaml` is ready, deploy it using `kubectl`:

    ```bash
    kubectl apply -f secrets.yaml
    ```

2. Next, deploy the application by applying the deployment manifest:

    ```bash
    kubectl apply -f node-red.yml
    ```
    
## License

node-red/node-red is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.
