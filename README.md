# ghost-operator
## Overview

`ghost-operator` is my first Kubernetes operator. It is designed to manage and automate the deployment of Ghost, a popular open-source blogging platform, on a Kubernetes cluster.

## Prerequisites

- Kubernetes cluster (v1.16+)
- kubectl configured to interact with your cluster
- Helm (v3+)
- Make (4.3+)

## Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/yourusername/ghost-operator.git
    cd ghost-operator
    ```

2. Deploy the Custom Resource Definitions (CRDs):

    ```sh
    make install
    ```

3. Deploy the operator:

    ```sh
    make deploy
    ```

## Usage

1. Create a Ghost instance by applying a custom resource:

    ```sh
    kubectl apply -f config/samples/blog_v1_ghost.yaml
    ```

2. Verify that the Ghost instance is running:

    ```sh
    kubectl get pods -l app=ghost
    ```

## Cleanup

To remove the operator and all associated resources:

1. Delete the Ghost custom resource:

    ```sh
    kubectl delete -f config/samples/blog_v1_ghost.yaml
    ```

2. Delete the operator:

    ```sh
    make undeploy
    ```

3. Delete the CRDs:

    ```sh
    make uninstall
    ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the Apache License 2.0.
