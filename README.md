# AzE2E: Azure Portal Deployment Templates


## Azure Portal

#### 0. Resource Group (Not Needed ~ Buggy)
[![Deploy to Azure Portal](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fresource-group.json)

[Visualize](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fresource-group.json) | [Edit](resource-group.json)

```
https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fresource-group.json
```

#### 1. Deploy Container Registry (Buggy)
[![Deploy to Azure Portal](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fcontainer-registry.json)

[Visualize](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fcontainer-registry.json) | [Edit](container-registry.json)

```
https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fcontainer-registry.json
```

#### 3. App Service Plan
[![Deploy to Azure Portal](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fapp-service-plan.json)

[Visualize](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fapp-service-plan.json) | [Edit](app-service-plan.json)

```
https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fapp-service-plan.json
```

#### 3. App Service
[![Deploy to Azure Portal](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fapp-service.json)

[Visualize](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fapp-service.json) | [Edit](app-service.json)

```
https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FChandraVijayDubey%2Faze2e%2Fmaster%2Fapp-service.json
```


## Azure DevOps

#### 0. Configure Project

- Setup Project: (https://dev.azure.com/organisation/project)
- Setup Azure DevOps Service Connection to Azure Portal: (https://dev.azure.com/organisation/project/_settings/adminservices)
	- #1: `Azure Resource Manager` & `Service principal (automatic)`
	- #2: `Docker Registry` & `Azure Container Registry`
	- `Authenticate` ~ watch out for browser's pop-up blocker
- Setup Agent Pool: (https://dev.azure.com/organisation/project/_settings/agentqueues)
	- Create PAT: (https://dev.azure.com/organisation/_usersSettings/tokens)
	- Set up a new self-hosted agent
		- Download the [setup file](https://vstsagentpackage.azureedge.net/agent/2.188.3/vsts-agent-osx-x64-2.188.3.tar.gz)
		- `./config.sh`
		- ```
			Enter server URL > https://dev.azure.com/organisation
			Enter authentication type (press enter for PAT) > PAT
			Enter personal access token > ***
			```
		- `./run.sh`
- Setup Repository: (https://dev.azure.com/organisation/_git/project)
- Setup Pipelines: (https://dev.azure.com/organisation/_git/project?path=%2Fazure-pipelines.yml)
- Setup Build & Release: (https://dev.azure.com/organisation/project/_build)
