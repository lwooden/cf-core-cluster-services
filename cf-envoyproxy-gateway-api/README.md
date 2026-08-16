## Deploying Envoy Proxy to Leverage Gateway API

# Prerequisites
1. AWS Loadbalancer Controller must be installed first and have the appropriate IRSA Role and permission for loadbalancer ensuring
2. The source of this chart is https://hub.docker.com/r/envoyproxy/gateway-helm/tags (it is container stored as an OCI artifact)  Enoy
3. This chart INSTALLS the CRDs for envoy and Gateway API

# Install Steps
1. Execute helm install
`helm install gateway . -n gateway --create-namespace`
1. Look in the root of the directory and install each manifest by number (1. EnvoyProxy, GatewayClass, Gateway, HTTPRoute)
2. HTTPRoute should be installed in the applications namespace (like ingress)
3. Explore keeping all of the routes in the gateway namespace for easier management (tls)
