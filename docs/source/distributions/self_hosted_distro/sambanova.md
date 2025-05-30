---
orphan: true
---
<!-- This file was auto-generated by distro_codegen.py, please edit source -->
# SambaNova Distribution

```{toctree}
:maxdepth: 2
:hidden:

self
```

The `llamastack/distribution-sambanova` distribution consists of the following provider configurations.

| API | Provider(s) |
|-----|-------------|
| agents | `inline::meta-reference` |
| inference | `remote::sambanova`, `inline::sentence-transformers` |
| safety | `remote::sambanova` |
| telemetry | `inline::meta-reference` |
| tool_runtime | `remote::brave-search`, `remote::tavily-search`, `inline::rag-runtime`, `remote::model-context-protocol`, `remote::wolfram-alpha` |
| vector_io | `inline::faiss`, `remote::chromadb`, `remote::pgvector` |


### Environment Variables

The following environment variables can be configured:

- `LLAMASTACK_PORT`: Port for the Llama Stack distribution server (default: `8321`)
- `SAMBANOVA_API_KEY`: SambaNova API Key (default: ``)

### Models

The following models are available by default:

- `sambanova/Meta-Llama-3.1-8B-Instruct (aliases: meta-llama/Llama-3.1-8B-Instruct)`
- `sambanova/Meta-Llama-3.1-405B-Instruct (aliases: meta-llama/Llama-3.1-405B-Instruct-FP8)`
- `sambanova/Meta-Llama-3.2-1B-Instruct (aliases: meta-llama/Llama-3.2-1B-Instruct)`
- `sambanova/Meta-Llama-3.2-3B-Instruct (aliases: meta-llama/Llama-3.2-3B-Instruct)`
- `sambanova/Meta-Llama-3.3-70B-Instruct (aliases: meta-llama/Llama-3.3-70B-Instruct)`
- `sambanova/Llama-3.2-11B-Vision-Instruct (aliases: meta-llama/Llama-3.2-11B-Vision-Instruct)`
- `sambanova/Llama-3.2-90B-Vision-Instruct (aliases: meta-llama/Llama-3.2-90B-Vision-Instruct)`
- `sambanova/Llama-4-Scout-17B-16E-Instruct (aliases: meta-llama/Llama-4-Scout-17B-16E-Instruct)`
- `sambanova/Llama-4-Maverick-17B-128E-Instruct (aliases: meta-llama/Llama-4-Maverick-17B-128E-Instruct)`
- `sambanova/Meta-Llama-Guard-3-8B (aliases: meta-llama/Llama-Guard-3-8B)`


### Prerequisite: API Keys

Make sure you have access to a SambaNova API Key. You can get one by visiting [SambaNova.ai](http://cloud.sambanova.ai?utm_source=llamastack&utm_medium=external&utm_campaign=cloud_signup).


## Running Llama Stack with SambaNova

You can do this via Conda (build code) or Docker which has a pre-built image.


### Via Docker

```bash
LLAMA_STACK_PORT=8321
llama stack build --template sambanova --image-type container
docker run \
  -it \
  -p $LLAMA_STACK_PORT:$LLAMA_STACK_PORT \
  -v ~/.llama:/root/.llama \
  distribution-sambanova \
  --port $LLAMA_STACK_PORT \
  --env SAMBANOVA_API_KEY=$SAMBANOVA_API_KEY
```


### Via Venv

```bash
llama stack build --template sambanova --image-type venv
llama stack run --image-type venv ~/.llama/distributions/sambanova/sambanova-run.yaml \
  --port $LLAMA_STACK_PORT \
  --env SAMBANOVA_API_KEY=$SAMBANOVA_API_KEY
```


### Via Conda

```bash
llama stack build --template sambanova --image-type conda
llama stack run --image-type conda ~/.llama/distributions/sambanova/sambanova-run.yaml \
  --port $LLAMA_STACK_PORT \
  --env SAMBANOVA_API_KEY=$SAMBANOVA_API_KEY
```
