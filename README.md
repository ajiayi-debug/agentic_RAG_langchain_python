# agentic_RAG

With reference from [langchain tutorial on agentic RAG](https://langchain-ai.github.io/langgraph/tutorials/rag/langgraph_agentic_rag/#graph)

Take note that Azure open ai was used (instead of open ai module ) and the ipynb in the tutorial is converted into a singular python script. I was unable to connect to langchain to pull prompt template so I manually created a file called [prompt_template](prompt_template.py) to insert the prompt template due to SSL certificate errors (potentially due to firewalls).

## requirements.txt
To start, run
````
pip install -r requirements.txt
````
In terminal to install all dependencies

## .env file

Do create a .env file with the following configurations:
````
LANGCHAIN_API_KEY=[langchain api key](https://docs.smith.langchain.com/how_to_guides/setup/create_account_api_key)
endpoint = [endpoint found in Azure AI Studios/ Resources and Keys/ Resource name/ </> View Code]
az_path = [path to azure cli which is found from typing `az where` in cmd, only necessary if device cannot find az cli]
ver=[api version of azure open ai api to be found in Azure AI Studios/ Resources and Keys/ Chat playground/ </> View Code]
embed_model=[deployment name of embedding model. I used text embedding 3 large]
gpt-4=[deployment name of gpt 4 model.]
gpt-35=[deployment name of gpt 3.5 turbo model.]
````

### (If device can find path to Azure CLI):
in [agentic_chunking_sample](agentic_chunking_sample.py), line 40-44:

Change 

```
az_path = os.getenv("az_path")

# Fetch Azure OpenAI access token
result = subprocess.run([az_path, 'account', 'get-access-token', '--resource', 'https://cognitiveservices.azure.com', '--query', 'accessToken', '-o', 'tsv'], stdout=subprocess.PIPE)
token = result.stdout.decode('utf-8').strip()
````

to 

````
result = subprocess.run(['az', 'account', 'get-access-token', '--resource', 'https://cognitiveservices.azure.com', '--query', 'accessToken', '-o', 'tsv'], stdout=subprocess.PIPE)
token = result.stdout.decode('utf-8').strip()
````
## Notes
This repo was created as a template for my other projects. I noticed that the output produced is slightly different from the tutorial, but the end result is the same in terms of generation. I am currently not too sure why and will need to investigate. 

