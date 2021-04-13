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

# Autocompletion
*~/.bashrc or ~/.bash_profile*
. <(flux completion bash)

# Create kind cluster
kind create cluster --config kind-config.yaml --name flux-cluster

# Check compability
flux check --pre

# Prequisites
Generate a personal access token (https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line)
Then set these variables
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>

# Initialize
flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=fleet-infra \
  --branch=master \
  --path=./k8s \
  --personal


# Initialize under organization
flux bootstrap github \
  --owner=<organization> \
  --repository=<repo-name> \
  --branch=<organization default branch> \
  --team=<team1-slug> \
  --team=<team2-slug> \
  --path=./clusters/my-cluster

# Set namespace
$env:FLUX_FORWARD_NAMESPACE="flux"


# More info
https://toolkit.fluxcd.io/get-started/