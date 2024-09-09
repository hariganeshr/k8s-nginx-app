
# Bootstrapping fluxcd toolkits in k8s cluster

flux bootstrap github \
 --owner=$GITHUB_USER \
 --repository=fluxcdInfraSOT \
 --branch=main \
 --path=deployinfra \
 --personal

# Define source SOT
flux create source git k8s_nginxapp_sot \
 --url=https://github.com/hariganeshr/k8s-nginx-appsot.git \
 --branch=main \
 --interval=30s \
 --export > ./deploy/flux_source.yaml
