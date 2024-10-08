## Multimodal AI

### What is Multimodal AI?
Multimodal AI refers to AI applications that can understand, interpret, and process information from multiple different modes or types of data. These modes can include text, images, audio, video data The ability to work with such diverse data types allows multimodal AI systems to perform more complex and nuanced tasks than unimodal systems, which are limited to a single type of data.

<img src="https://github.com/anuragsirish/multimodal-ai/assets/12818726/c59ea33e-5c3f-495f-92df-10026e576004" width="500" height="300">

## Use Cases 


| Title                   | Description                                                                                                                 |Code                                      | Link                                                                                                               |
| ------------------------------------------------------------| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -----------------------------------------------------------------------------------|------------------------------- |
| Real Estate Image Search| The real estate use case will show you how to search for different property images using text. Then it will also show to use a property image to search another similar property image. | In this scenario, we will use a custom embedding model provided by Azure AI vision wrapped in a Azure Function App. This function is called by a custom skillset created inside Azure AI search. | [My Jupyter Notebook](https://github.com/anuragsirish/multimodal-ai/blob/main/azure-search-vector-real-estate-1.ipynb) |


Inspired by Azure AI Search Samples from - https://github.com/Azure/azure-search-vector-samples/tree/main/demo-python
## Prerequisites

To run the Python samples in this folder, you should have:

- An Azure subscription, with [access to Azure OpenAI](https://aka.ms/oai/access).
- Azure AI Search, any tier, but choose a service that can handle the workload. We strongly recommend Basic or higher.
- Azure OpenAI is used in most samples. A deployment of the `text-embedding-ada-002` is a common requirement.
- Python (these instructions were tested with version 3.11.x)

You can use [Visual Studio Code with the Python extension](https://code.visualstudio.com/docs/python/python-tutorial) for these demos.

## Set up your environment

1. Clone this repository.

1. Create a `.env` based on the `code/.env-sample` file. Copy your new .env file to the folder containing your notebook and update the variables.

1. If you're using Visual Studio Code with the [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python), make sure you also have the [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter).

## Run the code

1. Open the `code` folder and sample subfolder. Open a `ipynb` file in Visual Studio Code.

1. Optionally, create a virtual environment so that you can control which package versions are used. Use Ctrl+shift+P to open a command palette. Search for `Python: Create environment`. Select `Venv` to create an environment within the current workspace.

1. Copy the `.env` file to the subfolder containing the notebook.

1. Execute the cells one by one, or select **Run** or Shift+Enter.

## Troubleshoot errors

If you get error 429 from Azure OpenAI, it means the resource is over capacity:

- Check the Activity Log of the Azure OpenAI service to see what else might be running.

- Check the Tokens Per Minute (TPM) on the deployed model. On a system that isn't running other jobs, a TPM of 33K or higher should be sufficient to generate vectors for the sample data. You can try a model with more capacity if 429 errors persist.

- Review these articles for information on rate limits: [Understanding rate limits](https://learn.microsoft.com/azure/ai-services/openai/how-to/quota?tabs=rest#understanding-rate-limits) and [A Guide to Azure OpenAI Service's Rate Limits and Monitoring](https://clemenssiebler.com/posts/understanding-azure-openai-rate-limits-monitoring/).
