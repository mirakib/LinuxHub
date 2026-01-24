<div align="center">
  <h1>Install the Azure CLI on Windows</h1>
</div>

The Azure Command-Line Interface (CLI) is a cross-platform command-line tool that can be installed locally on Windows computers.

## WinGet (Windows Package Manager)

```powershell
winget install --exact --id Microsoft.AzureCLI
```

The `--exact` option is to ensure the official Azure CLI package is installed. This command installs the latest version by default. To specify a version, add a `--version <version>` with your desired version to the command. Here's an example:

```powershell
winget install --exact --id Microsoft.AzureCLI --version 2.67.0
```

## Run the Azure CLI

```sh
az login
```

A common first step is to check your active subscription.
Azure CLI

```sh
az account show
```

## Update the Azure CLI

```sh
az upgrade
```


<div align="center">
  <h1>Install the Azure CLI on Linux</h1>
</div>


## Install with one command

```sh
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

[Step-by-step installation instructions](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest&pivots=apt#option-2-step-by-step-installation-instructions)

## Update Azure CLI

```sh
az upgrade
```

## Uninstall Azure CLI

```sh
sudo apt-get remove -y azure-cli
rm -rf ~/.azure
```
