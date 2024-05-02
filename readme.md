# Vector search in Python (Azure AI Search)

This repository contains notebooks to explore multimodal features of LLM models.                                                                                                                                                                                                                                                                 |
| [multimodal](./code/multimodal/azure-search-vector-image-index-creation-python-sample.ipynb)                                              | Vectorize images using [Azure AI Vision multimodal embedding](https://learn.microsoft.com/azure/ai-services/computer-vision/how-to/image-retrieval). In contrast with the multimodal-custom-skill example, this notebook uses the push API (no indexers or skillsets) for indexing. It calls the embedding model directly for a pure image vector search.                                                  |
| [multimodal-custom-skill](./code/multimodal-custom-skill/azure-search-vector-image-python-sample.ipynb)                                   | End-to-end text-to-image sample that creates and calls a custom embedding model using a custom skill. Includes source code for an Azure function that calls the [Azure AI Vision Image Retrieval REST API](https://learn.microsoft.com/rest/api/computervision/image-retrieval) for text-to-image vectorization. Includes an azure-search-vector-image notebook for all steps, from deployment to queries. |
                                                                                                                                                                                                                                                                    |

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
