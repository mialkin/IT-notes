# Flux

[↑ Flux](https://fluxcd.io/flux) is a tool for keeping Kubernetes clusters in sync with sources of configuration (like Git repositories), and automating updates to configuration when there is new code to deploy.

[↑ Get Started with Flux](https://fluxcd.io/flux/get-started)

Install Flux:

```bash
brew install fluxcd/tap/flux
```

Check if your Kubernetes cluster has everything needed to run Flux:

```bash
flux check --pre
```

Export your username and your [↑ access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token):

```bash
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>
```

Install Flux onto your cluster:

```bash
flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=fleet-infra \
  --branch=main \
  --path=./clusters/my-cluster \
  --personal
```

















In our example we are going to use [flux-get-started](https://github.com/fluxcd/flux-get-started). If you want to use that too, be sure to create a fork of it on GitHub.

Installing fluxctl on macOS:

```bash
brew install fluxctl
```

Create the flux namespace:

```bash
kubectl create ns flux
```

Then, install Flux in your cluster (replace YOURUSER with your GitHub username):

```bash
export GHUSER="YOURUSER"
fluxctl install \
--git-user=${GHUSER} \
--git-email=${GHUSER}@users.noreply.github.com \
--git-url=git@github.com:${GHUSER}/flux-get-started \
--git-path=namespaces,workloads \
--namespace=flux | kubectl apply -f -
```

`--git-path=namespaces,workloads`, is meant to exclude Helm manifests.

Wait for Flux to start:

```bash
kubectl -n flux rollout status deployment/flux
```

At startup Flux generates a SSH key and logs the public key. Find the SSH public key by running:

```bash
fluxctl identity --k8s-fwd-ns flux
```

Open GitHub, navigate to your fork, go to Setting > Deploy keys, click on Add deploy key, give it a Title, check Allow write access, paste the Flux public key and click Add key. See