# agentic_RAG

With reference from [langchain tutorial on agentic RAG](https://langchain-ai.github.io/langgraph/tutorials/rag/langgraph_agentic_rag/#graph)

Take note that Azure open ai was used (instead of open ai module ) and the ipynb in the tutorial is converted into a singular python script. I was unable to connect to langchain to pull prompt template so I manually created a file called [prompt_template](prompt_template.py) to insert the prompt template due to SSL certificate errors (potentially due to firewalls).

## .env file

Do create a .env file with the following configurations:
````
LANGCHAIN_API_KEY=[langchain api key](https://docs.smith.langchain.com/how_to_guides/setup/create_account_api_key)
endpoint = [endpoint found in Azure AI Studios/ Resources and Keys/ Resource name/ </> View Code]
az_path = [path to azure cli which is found from typing az where in cmd]
ver=[api version of azure open ai api to be found in Azure AI Studios/ Resources and Keys/ Chat playground/ </> View Code]
embed_model=[deployment name of embedding model. I used text embedding 3 large]
gpt-4=[deployment name of gpt 4 model]
gpt-35=[deployment name of gpt 3.5 turbo model]
````


