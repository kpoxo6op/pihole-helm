# Test Pi-Hole Helm from local PC

```sh
mkdir -p ~/code/pihole-helm && cd ~/code/pihole-helm
helm repo add mojo2600 https://mojo2600.github.io/pihole-kubernetes/
helm repo update
helm install pihole mojo2600/pihole --values values.yaml
```

## After making changes to values.yaml

```sh
helm upgrade --install pihole mojo2600/pihole -f values.yaml
kubectl get svc -n default
```
