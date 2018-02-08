

# Getting started with Kubernetes on Azure

Here are instructions on how to kickstart your work with Kubernetes on Azure. The information here will help get your local environment environment setup with all the necessary tools.

# Baseline Requirements

To start, you're going to need the following prerequisites:

* An Azure Subscription with Owner access (either for the subscription or a resource group)
* Azure CLI
* 

## Access to an Azure Subscription
You will need an Azure subscription either globally or via a Resource Group assigned to you from your organization to create the necessary cloud resources for Kubernetes.

_To create and destroy, you're going to need the `owner` role._

## Azure CLI

[Source documentation](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

_NOTE: The CLI will give you access to the acs and kubernetes (managed) sub-commands._

### macOS
Installing the CLI is as simple as:

```
brew update && brew install azure-cli
```

If you don't have Brew, [install homebrew](https://docs.brew.sh/Installation.html).

### Windows
For Windows users, go to the [documentation](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-windows?view=azure-cli-latest) and follow the instructions for installing through an MSI.

# Container / Kubernetes

## ACS Engine

Source: [GitHub repository](https://github.com/Azure/acs-engine) 

  > _TIP:_ The Azure Container Service Engine (acs-engine generates ARM (Azure Resource Manager) templates for Docker enabled clusters on Microsoft Azure with your choice of DCOS, Kubernetes, or Swarm orchestrators. 

### Installation

https://github.com/Azure/acs-engine/releases/download/v0.12.5/acs-engine-v0.12.5-darwin-amd64.tar.gz

#### macOS

1. Download the release
2. move it to your local optional install path
3. and make it available through bin

The script is below:

```
curl -L https://github.com/Azure/acs-engine/releases/download/v0.12.5/acs-engine-v0.12.5-darwin-amd64.tar.gz | tar xz
mv acs-engine-v0.12.5-darwin-amd64/ /usr/local/opt/acs-engine/
sudo ln -s /usr/local/opt/acs-engine/acs-engine /usr/local/bin/acs-engine
```

Confirm that acs-engine is installed:

```
acs-engine version
```

#### Windows

1. First, go to the [acs-engine release](https://github.com/Azure/acs-engine/releases) on GitHub and download the Windows specific zip.
2. Next, unzip it and put the contents in `"C:\ProgramData\acs-engine"`
3. Update your PATH environment variable to include the install location
4. open a PowerShell console and type `acs-engine version` to confirm installation
