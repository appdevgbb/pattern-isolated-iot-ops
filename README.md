# Pattern - Secure Kubernetes on the edge with Azure IoT Operations in an isolated network
An example of how to deploy Azure IoT Operations in an locked down network environment with kubernetes on the edge (k3s/AKS EE) and AKS in Azure. This guide explains how to configure a layered network in Azure IoT Operations. Layered networking allows you to manage network configurations, ensuring devices in different network layers can communicate effectively. It leverages services like CoreDNS for custom DNS resolution and Azure services for secure communication.

## Prerequisites

Before configuring the layered network, ensure you have:

- An active Azure subscription.
- Access to Azure IoT Operations.
- Admin privileges for creating resources.
- CoreDNS deployed in your environment (if not, follow [CoreDNS setup documentation](https://coredns.io/)).
- Basic understanding of networking concepts, including DNS and IP addressing.

### Steps to run this demo

To deploy the AKS clusters and set up Fleet Manager, follow these steps:

1. Clone this repository:

```bash
git clone https://github.com/appdevgbb/pattern-isolated-iot-ops.git
cd pattern-isolated-iot-ops
```

2. Deploy the AKS Clusters and Configure IoT Operations

Use the following command to deploy the AKS clusters and configure pattern-isolated-iot-ops along with the necessary Azure IoT Operations components:
```bash
./run.sh deploy
```

Monitor the progress of the deployment in the terminal.

3. To remove the entire deployment:

Run the following command:
```bash
./run.sh cleanup
```

Usage:

Usage: ./run.sh {deploy|cleanup}

This script automates the process of deploying two AKS clusters in the East and West US regions,
configures them with the pattern-isolated-iot-ops architecture, deploys Azure IoT Operations components
across both clusters, and peers the virtual networks between the clusters.

Commands:
  deploy     Set up the AKS clusters, deploy pattern-isolated-iot-ops, and configure Azure IoT Operations components.
  cleanup    Remove the AKS clusters, IoT Operations configurations, and all associated resources.

## Contributing
Contributions to this guide are welcome. Please submit a pull request or open an issue for any enhancements or corrections.
