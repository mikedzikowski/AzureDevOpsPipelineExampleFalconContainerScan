# AzureDevOpsPipelineExampleFalconContainerScan
An example Azure DevOps Pipeline that will scan a container image and conditionally push the image to an Azure Container Registry based on Image Assessment API policy response.

This pipeline leverages the FCS IaC tool to scan a DevOps repo, Falcon Cloud Security Image Assesment policies and Azure Container Registries to scan container images. Based on the API response the pipeline will conditionally build the image in a registry. By integrating these tools into a pipeline, developers will have the opportunity to address any security issues before deploying updates into their containers. 

The provided files can be imported into your ADO environment
* azure-pipelines.yml - pipeline steps 
* variables.yaml - defined variables used with the pipeline 

> [!NOTE]
>Required Service Connections in ADO:
>* Azure Resource Manager using service principal
>* Docker Registry
>
>[Manage Service Connections](https://learn.microsoft.com/en-us/azure/devops/pipelines/library/service-endpoints?view=azure-devops)

> [!IMPORTANT] 
>Image Assesment Policies 
> * The pipeline assumes image assesment policies have been defined in Falcon Cloud Security
>FCS Tool
> * The pipeline assumes the FCS (Falcon Cloud Security CLI for Linux x64) tool has been uploaded to a storage account for consumption of the pipeline - (See Tools Downloads in the Falcon Portal)


API Response True - Block Image build

![alt text](/images/failbuild.png)


API Response False - Allow Image build

![alt text](/images/allowbuild.png)
