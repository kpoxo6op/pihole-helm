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
```

## Test Values.yaml

```sh
helm template . --name-template pihole --namespace pihole --values values.yaml --debug
```

## Access Pi-hole

<http://192.168.1.122/admin>

## Password reset

```sh
kubectl get pods -n pihole
kubectl exec -it <pod> -n pihole -- bash
pihole -a -p
```
