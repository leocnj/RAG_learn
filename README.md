# RAG_learn
A learning project of RAG and LLM

## Steps

1) `html_dump.ipynb` downloads VA related HTML pages, extract their textual contents, chunk to 400-token pieces, and store to `train.jsonl` file

2) `rag_llama2.ipynb` 
- load `llama2-chat-hf` model. Since I am using a V100 card (32GB VRAM), to achive high performance and running speed, use `torch.float16`. If GPU VRAM is more limited, please consider 4bit or 8bit configurations.
- load `train.jsonl` file and create a vector store
- use `langchain` RAG implementation