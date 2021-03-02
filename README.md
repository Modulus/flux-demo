# Main website

https://fluxcd.io/

# Installing cli tools

1. Mac
```
brew install fluxcd/tap/flux
```

2. mac and others
```
curl -s https://toolkit.fluxcd.io/install.sh | sudo bash
```

# Create kind cluster
kind create cluster --config kind-config.yaml --name flux-cluster

# Check compability
flux check --pre