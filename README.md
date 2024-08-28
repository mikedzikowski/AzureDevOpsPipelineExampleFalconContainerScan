# AzureDevOpsPipelinExampleFalconContainerScan
An example Azure DevOps Pipeline that will scan a container image and conditionally push the image to an Azure Container Registry based on Image Assessment API policy response.

This pipeline leverages the FCS tool to scan a DevOps repo, Falcon Cloud Security Image Assesment policies and Azure Container Registries to scan a container images and based on an API response, conditionally build the image in a registry. This will give developers the abilitiy to resolve any findinds before pushing updates into their environment. 

API Response True - Block Image build

![alt text](/images/failbuild.png)


API Response False - Allow Image build

![alt text](/images/allowbuild.png)
