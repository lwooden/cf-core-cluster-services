## Container First Core Cluster Services Repo

# Update A Chart
1. `cd <chart>`
2. Edit the Chart.yaml and update the dependecy version to the target chart
3. `helm dep up`
4. Verify that the update helm chart tar.gz is in the /charts directory
5. Proceed with any updates to the overall values.yaml file

# Search for a chart
`helm search repo <REPO>`